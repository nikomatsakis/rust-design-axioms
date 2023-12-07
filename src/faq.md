# FAQ

## What are the axioms for?

The axioms are meant to capture and ake explicit the assumptions and intuitions that we use when building Rust. When making a decision, whether it's a question of language design or something else, we implicitly bring assumptions, intuitions, and hypotheses to bear, often without noticing. You might think, "*Hmm, maybe we could do X? Oh, but if we did that, it would mean Y, and I don't want that, scratch that idea.*" The goal for design axioms is to capture those moments -- whatever **Y** is right there, it's one of the **design axioms** we are using --- and write them out explicitly. Once we have the axioms written out, they can be used when facing future decisions. This in turn helps to bring alignment to a group of people by making those intutions explicit (and giving people a chance to refute or sharpen them). 

## Why do you call them design axioms? Aren't these the same as (tenets | guiding principles | whatever)?

The term *design axiom* is inspired by proof systems, where *axioms* are the things that you assert to be true and take on faith, and from which the rest of your argument follows. Our goal is to capture this for Rust: What are the starting assumptions that, followed to their conclusion, lead you to design Rust? The more clearly we can articulate those assumptions, the better we'll be able to ensure that we continue to follow them as we evolve Rust to meet future needs.

## I have some ideas for how to improve the axioms! How can I help?

See the [contributing](./contributing.md) section!
