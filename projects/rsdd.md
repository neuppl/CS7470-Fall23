# A brief overview of RSDD

RSDD is a Rust implementation of decision diagrams, more specifically binary decision diagrams (BDDs) and sentential decision diagrams (SDDs), two important compilation targets in propositional knowledge compilation. For this project we will be working exclusively with BDDs.

We will work with RSDD primarily through its OCaml bindings, but in this tutorial we will give a brief run-through of RSDD's implementation and usage in implementing `disc`.

## Installation

First, please install the bindings and pin them to your `disc` implementation through the instructions laid out at this link: [https://github.com/neuppl/rsdd-ocaml](https://github.com/neuppl/rsdd-ocaml). If we ever update this repository during the assignment, you will need to pull and redo the installation.

To test whether your install worked, copy the code snippet in the README of the `rsdd-ocaml` repository into `kc.ml`. If it builds/passes without warnings in an OCaml LSP you are set.

## Implementation Details of RSDD

RSDD's implementation of BDDs is specifically a **reduced ordered BDD (ROBDD)**, which enforces an order on the variables (which, in our case, is simply `int`) to maintain (1) a reduced form that factors variables, and (2) maintains canonicity--that is, for every variable order and propositional formula there exists a unique BDD up to logical equivalence.

You can (and should) look over the available library types and functions in `src/rsdd.ml` in the `rsdd-ocaml` repository. Some functions will not be directly applicable to the course, such as `rsdd_expected_utility`; feel free to disregard them. 

The implementation has three types that you will primarily be interfacing with.

1. `rsdd_bdd_builder` is a cache of variables and the operations on these variables. You can imagine this as a big BDD that includes all of the propositional formulae we've built up. 
2. `rsdd_bdd_ptr` is a pointer to a variable, on which the subtree represents one propositional formula. 
3. `rsdd_wmc_params_r` specifies parameters for weighted model counting, specifically with weights in the reals (as `float`s).

Here is some example ``rsdd-ocaml`` usage featuring all three types made explicits:

```ocaml
import Rsdd

(* 
    This is a pointer to a node of the BDD
    in which the formula defined by the subtree is label && label'. 
*)
let and_ptr : rsdd_bdd_ptr = 
    let bdd : rsdd_bdd_builder = mk_bdd_builder_default_order 0L in
    let (label , ptr) = bdd_new_var bdd true in
    let (label', ptr') = bdd_new_var bdd false in   
    bdd_and bdd ptr ptr'

(* 
    Here we define the WMC parameters. 
    The invariant enforced is that, for any label i,
    and for a (float * float) list L, 
    L[i] = (q, p) where Pr[not i] = q, and Pr[i] = p.
*)
let weights : rsdd_wmc_params_r = 
    let L =[(0.1, 0.9), (0.7, 0.3)] in new_wmc_params_r L

(*
    Now we can output a weighted model count, which calculates
    Pr[label && label'].
*)
let wmc_value : float = bdd_wmc and_ptr weights
(* or, if you want to convert to a Bignum.t, we can do this: *)
let wmc_value_t : Bignum.t = Bignum.of_float_decimal wmc_value
```

Below we outline some important library functions and what they do:

1. `mk_bdd_builder_default_order` takes in an `int64` $n$ (which you can specify by adding an L immediately after an `int`, as seen above) and initializes a `rsdd_bdd_builder` with $n$ many initial variables.
2. `bdd_new_var` allocates a new variable, its default truth value (which can be changed), and its variable name (label) and pointer.
3. `bdd_ite`, `bdd_or`, `bdd_and`, `bdd_negate` are hopefully self-explanatory; they perform the specified logical operations on the BDD.
4. `bdd_true` and `bdd_false` are pointers pointing to the true and false leaves of the `rsdd_bdd_builder`, respectively.
5. `new_wmc_params_r` makes a new `rsdd_wmc_params_r` value. It's the user's burden to enforce the invariant given in the above code snippet.
6. `bdd_wmc` performs the weighted model count.