# maru-bootstrap

"I make not to create but to know"

All ideas are stolen - these are stolen mostly from http://piumarta.com/software/maru/

maru-bootstrap is my effort to

1) understand the maru project more deeply
2) provide a more modular set of buildings blocks to bootstrap REAL
"personal computing" - see [modernity](https://github.com/strangemonad/modernity)

# Artifacts

The primary artifact is `maru-eval`, an interpreter for the maru s-expression
language.


# Aim

Adapt (recreate via transcribing or outright copying) the boostrapping portions of the maru 2.1 evaluator.

In particular, I want to understand how limited of a system you can
implement at this level that still provides enough power so that you can
describe the more powerful maru system (or modernity) in itself.

Maru s-expressions, as I understand them, are a minimal yet powerful
enough abstraction such that they can:

- Describe themselves
- Describe and even more powerful system (that can of course describe
  itself).

At some point, you want to have the self-describing powerful system
write its own compiler so you can ditch all the bootstrapping mechanism.


