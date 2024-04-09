# Being Rusty: Discovering Rust's design axioms

[WIP]: https://img.shields.io/badge/Status-WIP-yellow

To your average joe, being "rusty" is not seen as a good thing.
Being *R*usty -- with a capitol *R*! -- is, of course, something completely different!
So what is that makes Rust *Rust*?
The Rust Design Axioms repository is an attempt to articulate the answer.
**These axioms are a work in progress! [Please contribute your ideas on how to improve them!](./contributing.md)**

For more about the design axioms, see [this blog post introducing the idea]().

## How to structure the axioms?

There are a great number of "rules of thumb" and goals that we strive for. I'm actively debating the best way to structure the axioms. I'm updating this page to include a kind of "union" of different approaches.

## Rust's goal

My take on Rust's *mission statement* -- the thing we are trying to achieve -- is this variation of the slogan from the webpage:

**Empowering everyone to build reliable, efficient, and maintainable software**

The word "everyone" in this slogan does a lot of work. A key goal for Rust is to make the term "systems programming wizard" an anachronism. Today, if you want to do low-level systems programming, you have to keep so many things in your head that it crowds out the ability to focus on higher-level domains. This makes it very difficult to do both at once. Rust's goal is to provide structure and scaffolding so that, for most of your code, you can write high-level looking code and focus on the needs of your domain.

When you do need to drop down to low-level patterns, you should be able to do so, but in an encapsulated way that lets you build a performant, composable abstraction that will guide its users towards correctness. This way, when you are working with that interface, you don't have to be as cognizant or focused on the low-level details.

### What is empowerment?

I ponder sometimes the word *empowerment*. What does it mean exactly? To me it means three things (in order of precedence):

* **Lowering the barrier to entry.** It should be possible to get started very easily and get something that is 99% of what you want.
* **No ceiling.** The tool should scale to any use case. You shouldn't have to "graduate" to a more complex tool to get the "real work" done.
* **No complexity cliff.** You should be able to grow to more and more complex use cases without encountering a steep step up in complexity.

### Where is Rust a good choice?

Rust targets programs and domains where 

* reliability
* efficiency
* and long-term maintenance

are top priorities. For other domains, Rust may still be a great choice, but you may find that it adds a bit more overhead than you would like.

## What we strive for

This section is meant to capture
> **Note on status:** Some of the axioms are tagged with ![Confident][]. These are axioms that that I feel pretty good about and where I am pretty confident about where they fall in the ordering. Others are tagged as ![WIP][]. These are cases where the wording may need improvement and the ordering is less clear; some of them may want to be merged with others. --nikomatsakis

[Confident]: https://img.shields.io/badge/Status-Confident-darkgreen
[WIP]: https://img.shields.io/badge/Status-WIP-yellow

* ⚙️ **Reliability above all.** Rust users want to be sure their program will handle the edge cases that arise in production, not just the happy path. We guarantee memory safety and data-race freedom and look for opportunities to surface other problems wherever we can. ![Confident][]
* 🏎️ **Performant, composable abstractions.** We favor high-level APIs where the most convenient option is also the best one. The default style of writing things should be efficient and portable across operating systems and execution environments. We aren't explicit for the sake of being explicit, but rather to surface details we believe are needed. ![Confident][]
* 🔧 **Low-level control and transparency.** When building systems, it's often important to know what's going on underneath the abstractions. Abstractions should still leave the programmer feeling like they're in control of the underlying system, such as by making it easy to notice (or avoid) certain types of operations. ![Confident][] 
* 🌟 **Extensible and productive.** We empower our users to build their own abstractions. We prefer to let people build what they need than to try (and fail) to give them everything ourselves. ![Confident][]
* 🤸🏾 **Accessible and supportive.** Building reliable, efficient programs is ultimately a complex business. We can't always make Rust *easy*, but we can make it *supportive*. Our tooling aims to make "best practices" easy and convenient and, where choices are needed, to explain the choices and their implications as clearly as possible. Using Rust is a great way to level up your understanding of new domain or problem area. ![Confident][]

## Some of the rules we use for this

* **Design for the long term.** We aim When faced with tension
* **Target the extremes.** 
* **Not afraid to do the right thing.** We 
* **Learn from beginners.** We 


* **No required runtime.** It should also be possible to build Rust on bare metal without any operating system or supporting runtime. There should be "no room" for a language between Rust and inline assembly.
* **Not afraid to do the right thing.**

## How to read the axioms

**Ordering is significant.** Despite our best efforts, the axioms inevitably come into conflict. If we are forced to push, we prefer to satisfy the axioms that come earlier in the list. For example, accessibility ultimately trumps all, including reliability -- this is why we have a simple, workable type system that covers 99% of what you want and leave the rest to unsafe code, versus requiring full correctness proofs all the way down (but if we can make those proofs, so much the better!).

**The axioms capture beliefs about what Rust users value.** These axioms -- and especially their ordering -- are not universal. They are geared towards programs where performance, reliability, and long-term maintainence are top priorities. If these axioms don't sound like the right balance for your project, then Rust may not be the right choice.

**The axioms are not absolute.** To start, these axioms should be treated as a living document that can grow and change over time. But also, the axioms don't apply equally in all situations. For example, in some high-assurance domains, reliability takes precedence over accessibility; when designing aspects of Rust that are targeting those areas, it may make sense to develop more specialized versions of the axioms.

## How to contribute to the axioms

These axioms are a work in progress and we would very much like your help to make them better!
The [contribution page](./contributing.md) has instructions for how to participate.

--
 <p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/nikomatsakis/rust-design-axioms">Rust Design Axioms</a> is marked with <a href="http://creativecommons.org/publicdomain/zero/1.0?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC0 1.0 Universal<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/zero.svg?ref=chooser-v1"></a></p>
