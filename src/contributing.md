# Contributing to the axioms

These axioms are very much a work in progress -- and they always will be! We are actively soliciting contribution. For changes to the axioms themselves or the ordering between them, please [open an issue on our github repository](https://github.com/nikomatsakis/rust-design-axioms/issues/new/choose). When you do so, you'll be offered a choice between two issue templates:

* **Suggest a new axiom or a change to an axiom**-- what is some aspect of Rust's design that you feel is not explained by the existing axioms? Or perhaps you think the existing axioms could be changed or combined?
* **Suggest an example that supports or rebuts the current ordering** -- what is a part of Rust where two axioms were in tension, and which one got preference? Does that support the current ordering of the axioms?

For other changes, PRs against the site are welcome:

* Fixing typos
* Expanding on FIXME or TODO sections
* General improvements to the prose that don't change its meaning

## FAQ

Here are some guidelines for authoring or suggesting axioms.

### When does it make sense to split an axiom into two?

Oftentimes there are two aspects of Rust that could be combined into a single axiom or which could be separated, and it's a bit hard to know which you should do. In general, it makes sense to combine axioms together if they seem thematically related, because fewer axioms are better; but if these two aspects might be in tension with one another, or the precedence of one is different than the other, then we should break them out. 

As an example, I have currently made *productivity* one of Rust's design axioms, and in there I mention that, because we try to keep productivity high, we design for programs to be portable by default. But it's possible that portability should be broken out into its own axiom. The main reasons to do that would be if (a) portabiilty is in tension with productivity or (b) we give portability higher or lower precedence than we give other aspects of productivity.