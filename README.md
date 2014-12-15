SublimeCoq
==========

A Sublime Text package for writing Coq.

As it currently stands, this project just provides a very minimal syntax definition for Coq. It's by no means complete, having been written (a) by a relative Coq beginner, (b) by a beginner to writing SublimeText syntax definitions, and (c) at least initially, without a language reference (just off the top of my head). That being said, it's at least good enough to highlight your basic definitions and proofs such as

```coq
Inductive Nat: Set := 
  | Zero : Nat
  | Succ : Nat -> Nat.

Fixpoint plus_nat (n: Nat) (m: Nat): Nat :=
  match n with
  | Zero => m
  | S n' => S (plus_nat n' m)
  end.

Theorem plus_0_r: forall (n: Nat), plus_nat n 0 = n.
Proof.
  intros. induction n as [|n'].
  reflexivity.
  simpl. rewrite -> H. reflexivity.
Qed.
```

### Goals

In addition to providing a relatively comprehensive syntax defintion (omitting, of course, any respect to Coq `Notation`s), it is my goal at some point to add interactive prooving to the package in the style of Proof General. This may or may not be harder than it seems, and I don't really know how proof general does it currently. Certainly, it seems unlikely that, at least as long as the project remains just mine, that anything more than the absolute basics would be implemented. But even if I could just get it to step through proof states, that would be very useful in my book. Blasphemous as it may be to say it, I much prefer Sublime Text to emacs.

### Usage

The package is not available yet through Package Control, but all that is needed to make this project work is to copy (or symlink) the `Coq` folder in this repo to your local sublime text `Packages` folder. As of now, there's nothing but some basic syntax highlighting, but it's still better than nothing.
