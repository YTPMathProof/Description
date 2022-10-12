# Description

This markdown document attempts to describe the Math Proof Module

## Abstract

The Math Proof Module recieves an elementary math question and a student's work on that problem. It then generates feedback on that student's work, probably stopping on first error (much like a compiler's log).

## Example

### First stream of input (math question, in $\LaTeX$)

Prove that $a^2 + b^2 + c^2 \geq ab + bc + ca \forall a, b, c \in R$.

### Second stream of input (student's work, in $\LaTeX$)

Using Cauchy-Schwarz inequality, we have:

$$
a^2 + b^2 \geq 2ab
$$
$$
b^2 + c^2 \geq 2bc
$$
$$
c^2 + a^2 \geq 2ca
$$

Hence $(a^2 + b^2) + (b^2 + c^2) + (c^2 + a^2) \geq 2(ab+bc+ca).$

Dividing both sides of this inequality yields $a^2 + b^2 + c^2 \geq ab + bc + ca$.

### Expected stream of output (module's log)

Cauchy-Schwarz inequality is only applicable to non-negative real numbers.

## Notes

We think that the module can be broken down to 2 parts: Natural Language Processor and Math Validator.

The Natural Language Processor should break the student's mathematical proof down to seperate statements, and translate these statements and their relations to an intermediate language that is both human-readable and machine-readable.

The Math Validator should process the proof, now represented in the intermediate language, and give corresponding feedback.
