# GitPython-static-dynamic

*Preserving static type checking while adding attribute access deprecation
warnings to GitPython*

This is for testing how static type checking works in code that uses
[GitPython](https://github.com/gitpython-developers/GitPython) but is not part
of GitPython and does not use its specific `mypy` configuration. Its purpose is
to check that static type checking still works, and is able to find all the
same kinds of errors it was able to find before, even across **a specific
proposed change to GitPython** that adds some new dynamic behavior to warn on
access to some deprecated module attributes and a deprecated class attribute.

Because static analysis of code that uses a library does not always behave
quite the same inside a project as outside, **I developed these tests here
while experimenting with changes to GitPython**. These tests do not contain any
code copied or derived from GitPython, though they are themselves (with small
modifications) included in the change I am proposing to GitPython. For that
reason, and also to catch even static type errors from code not written
specifically to check for them, the tests developed here are not limited to
those of static behavior, but also test the relevant dynamic behavior.

This is not related to the dynamic attributes of `Git` *instances*, which is a
long-standing fundamental part of GitPython that is intended to remain
effectively unchanged both in its runtime behavior and in its treatment by
static type checkers.

---

This repository is licensed under [0BSD](https://spdx.org/licenses/0BSD.html),
a [“public domain
equivalent”](https://en.wikipedia.org/wiki/Public-domain-equivalent_license)
license that imposes no restrictions. This is the same license [used for code
examples in Python's
documentation](https://docs.python.org/3/license.html#terms-and-conditions-for-accessing-or-otherwise-using-python).
See [**`LICENSE`**](LICENSE).

Note that 0BSD is *not* the license of
[GitPython](https://github.com/gitpython-developers/GitPython) itself, only of
the contents of this repository, which contain no code first appearing in
GitPython. Code under 0BSD can be used in any way and included in software
distributed under any terms, even if I were not submitting it for inclusion in
GitPython (which I am).

All code in GitPython, including any code derived from this code, is licensed
[under its license
terms](https://github.com/gitpython-developers/GitPython/blob/main/LICENSE),
which are permissive but do impose some requirements, such as that of
preserving its license text.
