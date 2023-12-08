# Examples

This page contains examples that illustrate the axioms at work.
Some of these are things that we do (or choose not to do) because of the axioms.
But more interesting art the examples of where the axioms are in *tension*.

## Examples that exemplify the axioms

*Things we do (or choose not to do) because of the axioms*

## Examples that support the ordering

* "Accessible" over "Reliable"
    * Rust's pattern around unsafe code is an example where these came into tension and we let practicality win. We tried to build a safe type system that covers 95%-99% of the code you need to write, but which is by no means exhaustive. We let people vouch for the rest with minimal fuss or ceremony. It is certainly possible to build safer systems, either by requiring full proofs of correctness or by limiting the ability to write unsafe code, but we believe those options would be far less practical.
* "Reliable" over "Extensible"
    * We don't let users overload `&&` or `||` because they have special control-flow; we require macros to be marked with `!` so that users are aware they may not behave like a function call when it comes to control-flow.
* "Extensible" over "Transparent"
    * We have procedural macros, build.rs, and numerous mechanisms that let people generate large amounts of code.
* "Transparent" over "Productive"
    * No implicit memory allocation (e.g., `Box`)
    * Distinguishing `Rc` and `Arc`
* "Productive" over "Versatile"

## Counterexamples where we violated the ordering

* "Productive" over "Transparent" and, arguably, "Reliable"
    * Auto traits:
