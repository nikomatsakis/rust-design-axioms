# Being Rusty: Discovering Rust's design axioms

To your average joe, being "rusty" is not seen as a good thing.
Being *R*usty -- with a capitol *R*! -- is, of course, something completely different!
So what is that makes Rust *Rust*?
The Rust Design Axioms repository is an attempt to articulate the answer.
**These axioms are a work in progress! [Please contribute your ideas on how to improve them!](./contributing.md)**

For more about the design axioms, see [this blog post introducing the idea]().

## Rust's design axioms

> **Note on status:** Some of the axioms are tagged with ![Confident][]. These are axioms that that I feel pretty good about and where I am pretty confident about where they fall in the ordering. Others are tagged as ![WIP][]. These are cases where the wording may need improvement and the ordering is less clear; some of them may want to be merged with others. --nikomatsakis

[Confident]: https://img.shields.io/badge/Status-Confident-darkgreen
[WIP]: https://img.shields.io/badge/Status-WIP-yellow

We believe that...

* **Rust is meant to empower *everyone* to build reliable and efficient software,** so above all else, Rust needs to be **accessible** to a broad audience. We avoid designs that will be too complex to be used in practice. We build supportive tooling that not only points out potential mistakes but helps users understand and fix them. ![Confident][] 
* **Rust users want to surface problems as early as possible,** and so Rust is designed to be **reliable**. We make choices that help surface bugs earlier. We don't make guesses about what our users meant to do, we let them tell us, and we endeavor to make the meaning of code transparent to its reader. And we always, always guarantee memory safety and data-race freedom in safe Rust code. ![Confident][] 
* **Rust users are just as obsessed with quality as we are,** and so Rust is **extensible**. We empower our users to build their own abstractions. We prefer to let people build what they need than to try (and fail) to give them everything ourselves. ![Confident][] 
* **Systems programmers need to know what is happening and where,** and so system details and especially performance costs in Rust are **transparent and tunable**. When building systems, it's often important to know what's going on underneath the abstractions. Abstractions should still leave the programmer feeling like they're in control of the underlying system, such as by making it easy to notice (or avoid) certain types of operations. ![Confident][] 
* **Rust users want to focus on solving their problem, not the fiddly details,** so Rust is **productive**. We favor APIs where the most convenient and high-level option is also the most efficient one. We support portability across operating systems and execution environments by default. We aren't explicit for the sake of being explicit, but rather to surface details we believe are needed. ![WIP][]
* **N×M is bigger than N+M**, and so we design for **composability and orthogonality**. We are looking for features that tackle independent problems and build on one another, giving rise to N×M possibilities. ![WIP][]
* **It's nicer to use one language than two,** so Rust is **versatile**. Rust can't be the best at everything, but we can make it decent for just about anything, whether that's low-level C code or high-level scripting. ![WIP][]

...where earlier things take precedence.

## How to read the axioms

**Ordering is significant.** Despite our best efforts, the axioms inevitably come into conflict. If we are forced to push, we prefer to satisfy the axioms that come earlier in the list. For example, accessibility ultimately trumps all, including reliability -- this is why we have a simple, workable type system that covers 99% of what you want and leave the rest to unsafe code, versus requiring full correctness proofs all the way down (but if we can make those proofs, so much the better!).

**The axioms begin with a belief about the kinds of things Rust users value.** Each axiom begins with a core belief that identifies something that is important to Rust users. If these things don't sound like things you need for a project, then Rust may not be the right choice for that project.

**The axioms are not absolute.** To start, these axioms should be treated as a living document that can grow and change over time. But also, the axioms don't apply equally in all situations. For example, in some high-assurance domains, reliability takes precedence over accessibility; when designing aspects of Rust that are targeting those areas, it may make sense to develop more specialized versions of the axioms.

## How to contribute to the axioms

These axioms are a work in progress and we would very much like your help to make them better!
The [contribution page](./contributing.md) has instructions for how to participate.

--

 <p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/nikomatsakis/rust-design-axioms">Rust Design Axioms</a> is marked with <a href="http://creativecommons.org/publicdomain/zero/1.0?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC0 1.0 Universal<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/zero.svg?ref=chooser-v1"></a></p> 
