# Tmux urlview

Quickly open any url on your terminal window!

This is a fork of [tmux-plugins/tmux-urlview](https://github.com/tmux-plugins/tmux-urlview). The original upstream version is a wrapper around either [urlview](https://github.com/sigpipe/urlview) or [extract_url](http://www.memoryhole.net/~kyle/extract_url/). This fork adds flexibility in the form of a configuration option to choose a default program called, and allows for calling that program with command-line parameters.

### Demo (using urlview as the called program)

[![Demo tmux-urlview](http://g.recordit.co/5Uh5W4oaPR.gif)](http://recordit.co/5Uh5W4oaPR)

### Dependencies

*One* of the following is required.

- A program of your choice
- `urlview` - `brew install urlview` on OS X.
- `extract_url` - `brew install extract_url` on OS X.

### Key bindings

In any tmux mode:

- `u` - listing all urls on bottom pane


### Installation with [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @plugin 'tmux-plugins/tmux-urlview'


Hit `prefix + I` to fetch the plugin and source it. You should now be able to
use the plugin.

### Manual Installation

Clone the repo:

    $ git clone https://github.com/tmux-plugins/tmux-urlview ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/urlview.tmux

Reload TMUX environment:

    # type this in terminal
    $ tmux source-file ~/.tmux.conf

You should now be able to use the plugin.

### Configuration

> How can I change the default "u" key binding to something else? For example,
> key "x"?

Put `set -g @urlview-key 'x'` in `tmux.conf`.

> How can I use the default program FOO to get URLs explicitly?

Put `set -g @urlview-extractor 'FOO'` in `tmux.conf`. The default is
`urlview` if available, or `extract_url`.

> But I want to run FOO with command-line arguments '-a bar --b baz'!

Fine. Use `set -g @urlview-extractor 'FOO -a bar --b baz'`.

### Other goodies

`tmux-urlview` works great with:

- [tmux-fpp](https://github.com/tmux-plugins/tmux-fpp) - a plugin for
  opening any files on your terminal window
- [tmux-copycat](https://github.com/tmux-plugins/tmux-copycat) - a plugin for
  regex searches in tmux and fast match selection
- [tmux-yank](https://github.com/tmux-plugins/tmux-yank) - enables copying
  highlighted text to system clipboard

### License

[MIT](LICENSE.md)
