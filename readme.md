# Omarchy JSON Palettes #

## Problem ##

Omarchy ships ships themes with colors in `colors.toml` and a NeoVim editor theme.  Neovim editor themes contain colors not available in `colors.toml`.  Further, there is no mapping from `colors.toml` back to complex syntax highlighting for programming editors.

This is the "designation problem": shipping colors is insufficient.  In order to have uniformity, themes must also designate those colours.

## Solution ##

This repo contains all of Omarchy's official themes in [JSON Palette Format](https://github.com/frogtoss/palettetool/blob/main/docs/palette_format.md).  This format has the following benefits over colors.toml:

 1. Each color can be added to "hints", such as "identifier" or "selection", which makes extending the theme to new programs easy.
 2. Both the colors.toml colors and Neovim theme colors for each of palettes was merged
 3. JSON Palette format is easily read and written with color pipeline tool [https://github.com/frogtoss/palettetool](https://github.com/frogtoss/palettetool/blob/main/docs/palette_format.md "Palette Tool").  This allows for easy conversion.
 4. This repo contains every Omarchy theme in JSON Palette format, with color names, upscaled to 32-bits per channel.
 5. The JSON Palette format allows for the creation of lookup tables by hue or value (gradients) to allow fades and color transitions without leaving the palette colors.
 
## Bonus: Emacs Themes ##

To prove this works, I produced high quality Emacs themes from each of the JSON palettes and their hints.  These themes were generated from JSON Palettes. Far from being trivial conversions using `colors.toml`, they:

 - Use colors and syntax highlighting similar to Neovim
 - Support for advanced Emacs features like Doom modeline, org-mode and markdown-mode
 - Are compatible with tree-sitter's advanced faces

No support for Omarchy fonts or theme detection -- this is only colour themes.

Note: Author is aware that there is another set of Emacs Omarchy integrations at [https://github.com/scottjones/omarchy-emacs](https://github.com/frogtoss/palettetool/blob/main/docs/palette_format.md "this repo").  This is an alternative that uses the additional colors from Neovim.


## Credit ##

Credit goes to the original authors of the themes.  They are in a directory marked "official", which meas they are official themes. But I did not create them, and this is not an official Omarchy repo.

