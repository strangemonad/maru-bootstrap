# maru-bootstrap

"I make not to create but to know"

All ideas are stolen - these are stolen mostly from http://piumarta.com/software/maru/

Thoughts and comments (and where noted code) are my own.

maru-bootstrap is my effort to

1) understand the maru project more deeply

2) provide a more modular set of buildings blocks to bootstrap REAL
"personal computing" - see [modernity](https://github.com/strangemonad/modernity)

When exploring `maru-bootstrap` keep the following in mind: It will be thrown away!

In the end (beyond `maru-bootstrap`), we want to create a rich computing system.
Writing such a thing (anything really) in something as primitive as C (C++ sucks equally) is tedious
and not a great learning tool for people reading the code (the intent is hidden in
piles of accidental complexity).

Such a rich environment that also allows low-level access doesn't really exist. Python, Lisp, Smalltalk etc.
all make it hard to manage memory at a lower level more or less on
purpose. Go might be interesting to experiment with as an implementation
vehicle for this throw-away step.

# Artifacts

The primary artifact is `maru-eval`, an interpreter for the maru s-expression
language.

# Building

    ./configure [CFLAGS="-g -O0"]
    make

Standard social conventions for `autoconf` apply to the `configure` script

Building will produce a primitive maru s-expression evaluator + OO
runtime. On it's own, the environment has just the needed primitives
(actually quite a few more than just the bare minimum) to start
immediately crafting a richer environment in a richer, more-capable
language.

The `maru-eval` is hard coded to find a `boot.l` file in $PWD. Once
loaded, you're still in the maru-eval repl but have a much more capable
system. E.g.: you can define special forms and macros, have many useful forms
defined for you, can quote and quasi-quote, and all sorts of other
goodness.

# Usage

    maru-eval -b path/to/boot.l -

This will load the boot.l environment and then proceed to open a repl on
stdin.

If you simply want to run a script (or set of scripts):

    maru-eval -b path/to/script1 path/to/script/2 path/to/script/3

# Stop

OK, it's built, you can stop now. It's tempting to want to refine this -
it might even be edifying to recreate this a few times. But you'll get
most of that by going through the process of creating the rich-system
definition in a richer implementation vehicle. The "magic" mental step of going
from interpreter to dynamic compiler is pretty much the same in any
language (just like when you first grasp the concept of pointer /
reference  or Class vs Object).


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


