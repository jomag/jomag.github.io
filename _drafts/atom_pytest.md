Running PyTest in Atom
======================

I'm currently doing a lot of Python development. My editor of choice these
days is the [Atom editor](https://atom.io/) by GitHub.

For testing I primarily use [Pytest](http://doc.pytest.org/en/latest/),
mostly because I like the minimal boilerplate code needed.

One shortcoming of the Atom editor is that there is no plugin available
to run Python unit tests within the editor. There are a few that claims
to do it, but in my experience they don't work very well. There is however
a nice package called [Script](https://atom.io/packages/script) which can be
configured to run the current file. It automatically detects the file type,
so if it is a Python file it runs it with the Python interpreter.

But just running a Pytest test file does not do much: the test functions
are declared but they are not called.

To fix that I add the following to each test file:

~~~python
if __name__ == "__main__":
    pytest.main([__file__, '--color=yes', '-x'])
~~~

Now when Script runs this file, it runs pytest on itself.

There's one problem: if the test file depends on pytest to initialize
before the file is executed it may fail. For example if one of the
imports requires Pytest to initialize first the imports may fail.

The fix is to put the pytest invocation at the very top of the file,
before any imports that may fail.
