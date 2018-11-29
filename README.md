# self.wiki

[self.wiki] is a wiki and todo manager.
I wanted to be able to write notes, documentation, and tasks from a simple (understand: minimal) interface, using
mostly keyboard shortcuts.

Here's what my feature list draft looked like:

- [x] Create wikis directly from URL (`ctrl+l`, then type stuff, on most browsers)
    - [x] On any URLs. i should not be restricted to naming stuff (restricted names are `/todo`, `/**/edit`,
      `/**/edit/save`, `/**/edit/delete`)
- [x] Wikis should be more or less standard extended markdown
- [x] Wikis should be stored on the filesystem **as-is**, no database or stuff like that.
  I should be able to read them using `less` when i want to.
- [x] Should not make calls to the outside world, except on linked stuff.
- [x] At least todo operations should have keyboard shortcuts
    - [x] add
    - [ ] delete
    - [ ] update status
- [ ] I should be able to navigate links without using weird browsers like [`uzbl`]

That's more or less it.

I looked at several other solutions, including [tiddlywiki], but it was too mouse-based for my tastes.

## Installation
Install using pip, using the `master` branch, or by picking a release in the [releases] tab:

    pip install https://vit.am/gitea/paulollivier/self-dot-wiki/archive/master.tar.gz

Then, simply run the included script:

    $ self.wiki --help
    usage: self.wiki [-h] [--debug] [--host HOST] [-p PORT]

    optional arguments:
      -h, --help            show this help message and exit
      --debug               Turns on debug mode
      --host HOST           address to bind on
      -p PORT, --port PORT  Port to listen on

## Configuration

Configuration is kept to a minimum. There is a single configurable environment variable: `SELF_WIKI_CONTENT_ROOT`,
defaulted to `~/.self.wiki`. [self.wiki] will store its markdown files there.

[self.wiki]: https://vit.am/gitea/paulollivier/self-dot-wiki
[releases]: https://vit.am/gitea/paulollivier/self-dot-wiki/realeases
[`uzbl`]: https://www.uzbl.org/
[tiddlywiki]: https://tiddlywiki.com/