# How to Create Palette JSON Files From Themes #

Documenting how I create new palette json files from themes because I am very likely to just forget.

The basic idea: create two palette.json files, one from toml and one from the Neovim extractor. Then, merge them together.

1. from palettetool, run `tools/neovim/batch_export.sh` to export the current Neovim theme.

2. from palettetool, run `tools/omarchy/import_colors.py` to the Omarcy theme colors

3. from palettetool, run `tools/omarchy/merge_theme_sources.py --from-toml theme-toml.pal.json --from-neovim theme-neovim.pal.json`

4. use Book of Colours to modify them.  The standard way:
  - Rename theme to remove 'merged' from name
  - Select all colors that are not part of the first 16 and use auto-namer
  - Create dither pair 'fgbg' with foregound and background colors
  - Create 'Hue by 16' gradient, sorted colors by hue for the base 16 colors
  
5. Work on hints and designation
  - Load the theme up in Neovim and compare to the exported emacs theme
  - Common tweak points: 'normal', 'comment' background, string, title and preprocessor all need improvement.
  

## PaletteTool Usage ##

```bash
cd palettetool

tools/neovim/batch_export.sh
cp white.pal.json /tmp/themes/white-neovim.pal.json

tools/omarchy/import_colors.py ~/.local/share/omarchy/themes/white/colors.toml -o /tmp/themes/white-toml.pal.json

tools/omarchy/merge_theme_sources.py --from-toml /tmp/themes/white-toml.pal.json --from-neovim /tmp/themes/white-neovim.pal.json -o white.pal.json
```
 
