# fonts

play with fonts.

## Softwares

- Fontforge


## Operational

### Convert OTF to TTF

[Source Han Serif (Source Han Serif | 思源宋体 | 思源宋體 | 源ノ明朝 | 본명조)](https://github.com/adobe-fonts/source-han-serif) is great font powered by Adobe and Google, which supports well in English, Simplifed Chinese, Traditional Chinese, Japanese and Korean.

But its releases only provide Open Type format fonts, for the ease of use (web pages, 3rd party libs only support ttf), we need to convert OTF format to TTF format.

Prerequisites:

- [otfcc](https://github.com/caryll/otfcc) installed by brew
- [otfcc-c2q](https://github.com/caryll/otfcc-cubic2quad) installed by npm

Command:

    otfccdump input.otf | otfcc-c2q | otfccbuild -o output.ttf

Disadvantage: otfcc-c2q is based on Node.js, which doesn't support strings length greater than 260000000 (260M) due to its V8 engine. Therefore if you want to convert large-size fonts (>15M), you need to split font into pieces, then convert to ttf, and then merge pieces all together.

### Merge Fonts (with Fontforge)

- Step 1. Edit font-merge.pe
- Step 2. fontforge -script font-merge.pe

Reference: [Merging Font with FontForge](http://7thgen.info/blog/2008/07/merging-font-with-fontforge/)
