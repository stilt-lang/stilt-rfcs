- Status: draft
- Number: 0000
- Author: your name and GitHub login
- Edition: the first edition that has the change, if it belongs to one
- Pull request: link, once it is open
- Tracking issue: link, once it is accepted

# Title: the feature in a few words

## Summary

Two or three sentences: what the language gains or changes.

## A plain example

The program a user would write, in full, as the Reference's conformance tests would hold it.

```stilt
// The smallest program that shows the feature at work.
```

What it does: what the program prints or returns, and what `stilt show` reports about it, if the feature changes the facts.

What goes wrong without the feature: the program the user has to write instead, or the mistake they make, shown in code, with what it costs them: lines, a lost guarantee, a runtime failure.

## Motivation

Who needs this and how often, with two or three more examples from real programs. Say what the feature is not for.

## The rules

The change to the Reference, as a diff. For each chapter it touches, the paragraphs added, changed or removed, with their IDs, in the Reference's own words:

```diff
 {#chapter.paragraph-id}
-The sentence as it is.
+The sentence as it becomes.
```

State how the change interacts with inference, effects, modes, facts, `without`, the standard library and the grammar. A removed paragraph keeps its ID, marked removed. List the conformance tests that the new paragraphs need: for each paragraph that rejects programs, one program accepted and one rejected.

## The error tax

Draft diagnostics for the feature's common mistakes: at least the three a person is likeliest to make. Each shows the program, the code and the message in the form the compiler prints, and the fix in the code. If the feature adds a diagnostic code, say which paragraph is its home.

```text
error[E0000]: the message, in under 40 tokens
  --> main.lt:3:5
   |
 3 |     the line that is wrong
   |     ^^^^^^^^^^^^^^^^^^^^^^ what is wrong here
   |
help: the fix, shown in the code
```

An RFC without these isn't ready.

## Compatibility

- Does it break any program that is valid today? Which, and why it is acceptable.
- Which edition does it belong to?
- What does the `stilt migrate` rewrite do to a program that crosses it? Show a before and an after.
- What does it change in the API of a package: does it make a fact part of an API that was not, or the other way round?

## Alternatives

The designs that were considered and why each lost, including doing nothing. Say what you would give up with the winner.

## Unresolved questions

What is open, and which of it must be settled before the RFC is accepted, before it is implemented, or before it is released.
