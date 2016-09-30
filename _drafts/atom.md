My basic Atom setup
===================

I enjoy Atom since it out of the box is quite sane and partially keeps me
from endless configuration and tuning, letting me do real work instead.

Unfortunately, one of the areas where Atom does not shine is when you are
working on multiple computers. With Emacs and Vim I used to put my configuration
in Dropbox and just link them to my homedirectory and I was ready to go on
a new computer. Not so much with Atom since the config directory is typically
at least 10's of megabytes and I've had bad experiences sharing them between
different computers and platforms.

Luckily it's very quick to get up to speed on a new Atom installation.
Here's some of the customizations I typically do:

Disable tabs
------------

I never use tabs to find an open file. Instead I use Fuzzy Finder (`⌘T`)
to open the file I need. It's typically much faster when you're working
on a project with lots of files.

And then the tabs just take up visual space. The tabs can be removed by
disabling the builting `tabs` package.

One downside of this is that it is a bit harder to see what file is open in
each pane. The file in the current pane can be seen in the status bar, but
you have to switch focus to the other panes to see what is open in them.

There's a package, `pane-info` that displays the filename for each pane
at the top right. It's very minimal but it gets the work done.

Use tmux key bindings
---------------------

I spend much time in the terminal and typically use `tmux` all the time.
I've configured atom to use the same key bindings:

'body':
  'ctrl-b %': 'pane:split-down-and-copy-active-item'
  'ctrl-b "': 'pane:split-right-and-copy-active-item'
  'ctrl-b x': 'pane:close'
  'ctrl-b o': 'window:focus-next-pane'
  'ctrl-b up': 'window:focus-pane-above'
  'ctrl-b down': 'window:focus-pane-below'
  'ctrl-b left': 'window:focus-pane-on-left'
  'ctrl-b right': 'window:focus-pane-on-right'

Save all by default
-------------------

I think it's sane to change the default save behavior to "save all". It
happened too often that I saved a file and tried to run it in the terminal,
just to find that I had forgotten to save a bunch of other files.

It almost never happens that I *don't* want to save all file changes at once.

For some reason I've had problems changing this functionality. But this
configuration seems to work everywhere:

'body':
  'alt-cmd-s': 'window:save'
  'cmd-s': 'window:save-all'

'.platform-linux atom-text-editor':
  'ctrl-s': 'unset!'
  'ctrl-s': 'window:save-all'

'.platform-darwin atom-text-editor':
  'cmd-s': 'window:save-all'


Pylint
------

I spend a lot of time writing Python these days and a linter is great to
quickly get notified of obvious typos etc.

Luckily there's a great linter framework available for Atom. The base
package is called `linter`, but for some reason it does not show up
when searching for `linter` in Atom. I use `apm install linter` to install it.

The `linter` package depends on plugins to provide support for different
languages. For Python I use the packages `linter-pep8` and `linter-pylint`.

They both require that the `pylint` and `pep8` tools are installed. They can be
installed using either `apt-get` on Debian systems or `pip`:

~~~
pip install pylint
pip install pep8
~~~


Git
---

For Git functionality I use two packages: `git-plus` to get access to basic
git commands (add, commit, pull, push, ...) and `language-git` to get
syntax highlighting when writing git commit messages.
