# BYN Symbol — Belarusian Ruble Sign Font

An open-source companion font for the **Belarusian ruble currency sign (BYN)**. Use the mark alongside an existing typeface in websites, product prices, documents, presentations, design files and print.

This repository contains a Montserrat-based prototype, variable and static font exports, and the editable Glyphs source. It is intended for designers and developers who need a practical way to typeset the new Belarusian ruble sign before native font and operating-system support becomes widespread.

> [!IMPORTANT]
> **Current build limitation:** the exported sign is currently mapped to Cyrillic capital letter **Б (U+0411)** as a temporary visual workaround. It is **not yet mapped to the dedicated Belarusian Ruble Sign code point U+20C5**. Apply this font only to the single currency-sign character — never to ordinary Cyrillic text. The current build is not suitable for semantic text interchange or copy/paste workflows that require a dedicated currency character.

## Download

- **[Variable font — TTF](fonts/variable/BYNsymbol-VariableVF.ttf)**
- **[Variable font — WOFF](fonts/variable/BYNsymbol-VariableVF.woff)**
- **[Static OTF and WOFF files](fonts/static/)**
- **[Editable Glyphs source](sources/BYN%20symbol.glyphs)**
- **[Usage guide](docs/usage.md)**

## What it solves

The National Bank of the Republic of Belarus approved a new graphic symbol for the Belarusian ruble in January 2026. The Unicode Consortium has accepted **U+20C5 BELARUSIAN RUBLE SIGN** for inclusion in Unicode 19.0. As of November 2026, Unicode 19.0 is still in preparation, and native support across operating systems, applications and installed fonts is not yet universal.

This project is an interim typographic tool: it lets you place the sign as a separate glyph without changing the main font used for the rest of a layout.

- **For designers:** use the sign in Figma, Adobe apps and other desktop tools that support installed fonts.
- **For developers:** embed the WOFF font in a website with CSS @font-face.
- **For documents and print:** use the TTF or OTF files in applications that support custom fonts.
- **For price displays:** the source includes figures and basic punctuation for testing numeric combinations.

This is an independent community font project, not an official font release by the National Bank of Belarus or the Unicode Consortium.

## Current contents and status

| Asset | Current status |
|---|---|
| Variable TTF | Available |
| Variable WOFF | Available |
| Static OTF / WOFF | Thin, Light, Regular, Bold and Black |
| Editable source | Glyphs file in sources/ |
| Figures | 0–9 |
| Punctuation | Space, period and comma |
| Weight axis (wght) | Defined in the variable source |
| Slant axis (slnt) | Experimental; the BYN sign still needs a dedicated slanted design |
| Contrast axis | Not included yet |
| Unicode U+20C5 mapping | Planned; not included in the current exports |
| WOFF2 / SVG / PNG | Planned |

The current font is a **companion symbol font**, not a full text family. It is designed to be applied to the currency sign itself.

## Quick start

### Desktop: Figma, Adobe apps, Office and print

1. Download the [variable TTF](fonts/variable/BYNsymbol-VariableVF.ttf) or a static OTF from the static fonts folder.
2. Install the font in your operating system.
3. In your text, select only the character **Б** (Cyrillic capital letter U+0411).
4. Apply **BYN Symbol** to that character.

Because U+0411 is the temporary character slot in this build, any ordinary letter Б formatted with this font will also turn into the currency sign. Keep the font applied only to the intended symbol.

### Web: CSS @font-face

Place the font files in your web project and register the WOFF file:

~~~css
@font-face {
  font-family: "BYN Symbol";
  src: url("./fonts/BYNsymbol-VariableVF.woff") format("woff");
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}

.byn-symbol {
  font-family: "BYN Symbol", sans-serif;
  font-weight: 400;
}
~~~

Use the temporary glyph in a dedicated span:

~~~html
<p>1 250 <span class="byn-symbol" aria-label="Belarusian ruble">Б</span></p>
~~~

Adjust the weight with the normal CSS font-weight property. The slant axis is not yet validated for the BYN sign itself.

For complete desktop, web and print instructions, see the [usage guide](docs/usage.md).

## Unicode status: U+20C5

The official character name is **BELARUSIAN RUBLE SIGN** and its current proposed code point is **U+20C5**.

On 28 October 2026, the Unicode Technical Committee accepted U+20C5 for publication in Unicode 19.0. The Unicode Pipeline still cautions that accepted characters and code points can change before the repertoire is frozen for publication. The current font files in this repository do not yet include the U+20C5 mapping.

- [Unicode Pipeline — current character status](https://www.unicode.org/alloc/Pipeline.html)
- [Approved UTC minutes documenting the initial assignment](https://www.unicode.org/L2/L2026/26093.htm)
- [National Bank of Belarus — BYN symbol](https://www.nbrb.by/engl/coinsbanknotes/byn-ico)

**Recommended next step:** add U+20C5 as the primary mapping, retain U+0411 only as an optional visual alternate if useful, and test the result in browsers and desktop applications. Do not use U+0411 as the long-term text encoding for the currency sign.

## Roadmap

- [ ] Add the dedicated U+20C5 glyph mapping.
- [ ] Keep the ordinary Cyrillic letter Б separate from the currency sign.
- [ ] Complete the variable axes for the sign: weight, contrast and slant.
- [ ] Add an optional OpenType stylistic alternate (ss01 / salt) for controlled typographic use.
- [ ] Export WOFF2 and refreshed static files.
- [ ] Add SVG and PNG downloads for users who do not want to install a font.
- [ ] Expand browser, Windows, macOS, Figma and print proofs.
- [ ] Publish a visual specimen and a tagged release.

## License and commercial use

The font software is distributed under the [SIL Open Font License 1.1](OFL-1.1.txt).

OFL permits commercial use, embedding, modification and redistribution under its terms. **The font software itself cannot be sold as a standalone product.** It can be bundled with software or another product. Paid services around the font — such as implementation, custom optical fitting, CMS integration or support — are a different offering.

The project identifies Montserrat as its base. Before distributing further modified builds, preserve the applicable upstream attribution and license notices for the exact Montserrat source used.

## По-русски

**BYN Symbol** — открытый шрифтовой проект для набора нового знака белорусского рубля в интерфейсах, документах, макетах и печати.

Сейчас в сборке знак временно назначен на кириллическую заглавную **Б (U+0411)**. Это позволяет визуально вставить знак через отдельный шрифт, но не является полноценной Unicode-кодировкой валютного символа. Применяйте BYN Symbol только к выделенному знаку, а не ко всему тексту: обычная буква «Б» в этом шрифте тоже будет отображаться как знак рубля.

Для корректного обмена текстом целевая кодировка — **U+20C5 BELARUSIAN RUBLE SIGN**. Код принят для включения в Unicode 19.0, но текущие файлы репозитория ещё не содержат этого маппинга.

В репозитории доступны variable TTF/WOFF, статические OTF/WOFF и исходник Glyphs. Подробности установки и использования — в [руководстве](docs/usage.md).

**Поисковые запросы:** символ белорусского рубля, знак белорусского рубля, шрифт символа BYN, шрифт белорусского рубля, как вставить символ белорусского рубля, Belarusian ruble sign font, BYN currency symbol font, U+20C5 font.

## Contributing

Issues and pull requests are welcome. Please include a rendering proof and the application / operating system used when reporting a font issue.
