# Miss - Unsaved Files Manager

![Neovim](https://img.shields.io/badge/Neovim-%3E=0.5-blue.svg)

Miss helps manage unsaved files. It provides a popup window listing all modified buffers, allowing you to quickly save or open them in new tabs.

## Features

- Lists all unsaved files in a floating popup window.
- Save selected files directly from the popup.
- Reset all changes from selected file from the popup.
- Open selected files in a new tab.
- Safety run user commands as a callback if there are unsaved files.
- Easy-to-use keybindings.

## Installation

### Using `packer.nvim`

```lua
use 'Enigama/miss.nvim'
```

### Using `vim-plug`

```vim
Plug 'Enigama/miss.nvim'
```

## Usage

Use the default keybinding:

```vim
<leader>a
```

Could be used for git status safety:

```
keymap("n", "<leader>gs", function()
    require("miss").has_missed_files(function()
        vim.cmd(":G")
    end)
end, opts)
```

## Keybindings

| Key            | Action                                          |
| -------------- | ----------------------------------------------- |
| `<leader>a`    | Show popup with unsaved files                   |
| `s`            | Save selected file and refresh list             |
| `<CR>` (Enter) | Open selected file in a new tab                 |
| `x`            | Reset changes of selected file and refresh list |
| `q`            | Close the popup                                 |

## Configuration

Miss works out of the box but can be initialized manually:

```lua
require('miss').setup()
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
