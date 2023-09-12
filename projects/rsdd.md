# A brief overview of RSDD

RSDD is a Rust implementation of decision diagrams, more specifically binary decision diagrams (BDDs) and sentential decision diagrams (SDDs), two important compilation targets in propositional knowledge compilation. For this project we will be working exclusively with BDDs.

We will work with RSDD primarily through its OCaml bindings, but in this tutorial we will give a brief run-through of RSDD's implementation and usage in implementing `disc`.

## Installation

First, please install the bindings and pin them to your `disc` implementation through the instructions laid out at this link: [https://github.com/neuppl/rsdd-ocaml](https://github.com/neuppl/rsdd-ocaml). If we ever update this repository during the assignment, you will need to pull and redo the installation.

To test whether your install worked, copy the code snippet in the README of the `rsdd-ocaml` repository into `kc.ml`. If it builds/passes without warnings in an OCaml LSP.

## Implementation Details of RSDD

RSDD's implementation of BDDs is specifically a **reduced ordered BDD (ROBDD)**, which enforces an order on the variables (which, in our case, is simply `int`) to maintain (1) a reduced form that factors variables, and (2) maintains canonicity--that is, for every variable order and propositional formula there exists a unique BDD up to logical equivalence.

The implementation has two components that you will primarily be interfacing with.

1. The `rsdd_bdd_builder` is a cache of variables and the operations on these variables. You can imagine this as a big BDD that includes all of the propositional formulae we've built up. 
2. The `rsdd_bdd_ptr` is a pointer to a variable, on which the subtree represents one propositional formula. 

So consider the following OCaml code:

