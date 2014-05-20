# Tmux Pain Control

Tmux plugin for controlling panes. Adds standard pane navigation bindings.

So far, you had to google around and comb other people's dotfiles to find these.
This plugin hopefully makes them more available and "more standard".

Thanks to the Tmux community for "inventing" these bindings. I've merely just
copied them here.

### Bindings

Notice most of the bindings emulate vim cursor movements.

**Navigation**

- `h` - select pane on the left
- `j` - select pane below the current one
- `k` - select pane above
- `l` - select pane on the right

**Resizing panes**

- `H` - resize current pane 5 cells to the left
- `J` - resize 5 cells in the up direction
- `K` - resize 5 cells in the down direction
- `L` - resize 5 cells to the right

The amount of cells to resize can be configured with `@pane_resize` option. See
[configuration section](#configuration) for the details.

**Splitting panes**

- `|` - split current pane horizontally
- `-` - split current pane vertically

### Installation with [Tmux Plugin Manager](https://github.com/bruno-/tpm) (recommended)

Add plugin to the list of TPM plugins in `.tmux.conf`:

    set -g @tpm_plugins "              \
      bruno-/tpm                       \
      bruno-/tmux_pain_control         \
    "

Hit `prefix + I` to fetch the plugin and source it.

You should now have all `pain_control` bindings defined.

### Manual Installation

Clone the repo:

    $ git clone https://github.com/bruno-/tmux_pain_control ~/clone/path

Add this line to the bottom of `.tmux.conf`:

    run-shell ~/clone/path/pain_control.tmux

Reload TMUX environment:

    # type this in terminal
    $ tmux source-file ~/.tmux.conf

You should now have all `pain_control` bindings defined.

### Configuration

You can set `@pane_resize` Tmux option to choose number of resize cells for the
resize bindings. "5" is the default.

Example:

    set-option -g @pane_resize "10"

### License
[MIT](LICENSE.md)