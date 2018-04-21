# Setting Type to be Read

### Relatives units
`em`, `rem`, `ch`

### Three legs of readability "stool"
1. Measure (length of a line)  
Implemented by `max-width`
45-75 characters including spaces. 22-38 em  
2. Text size  
Implemented by `font-size`
When finding equivalent text size for a different font, use x-height.
3. Line spacing (leading)  
Implemented by `line-height`
Use unit less measure: `line-height: 1.5`. Do not use `150%` or `1.5em`. Using any unit will cause the line height to be calculated into pixel values on the element that the line height is specificed. Instead, we need to calculate line height relatively for each child.

Goal: achieve even type color (greyness when squiting at the block of text)

### Alignment and hyphenation
1. Don't justify last line (default behavior). Override default: `text-align-last: justify`
2. When justifying content, use hyphens to manually separate parts in made up word. (see cheat sheet)
3. Use `<wbr>` to separate segments of long url so they can wrap around
4. Use `<html lang="ISOLanguageTag-COUNTRYCODE">` for proper auto hyphen generation
5. Use `hyphens: auto` to auto generate hyphens
6. Use `hyphens: manual` to avoid auto hyphens for people's names, acronyms, manually typed in hyphens
7. Use `hyphenate-limit-lines` to avoid "ladder" of hyphens on the right. Recommended value: `2`
8. Use `hyphenate-limit-chars` to optimize each for each word: min-length for a hyphenable word, min-length for pre-hyphen string, min-length for post-hyphen string. Recommended value: `6 3 2`. Depending on the style guide, leave it to `auto` (the default) may also work.
9. Use `hyphenate-limit-zone` to control the number of hyphens (but increase rag on the right). Recommended value: `8%`
10. Use `hyphenate-limit-last` to avoid hyphenating last word

### Responsive paragraphs
1. use `<meta name="viewport" content="width=device-width, initial-scale=1.0">` to prevent phones faking to be a large viewport that requires zooming
2. use `em` to measure screenwidth. Increased font-size is equivalent to smaller screen. They both should affect breakpoint detection
3. adjust font-size according to reading distance: longer distance -> larger font
4. tablet problem: breakfast (far), knee (middle), bed (near)

# Typographic Detail

### Symbols, signs and accets
1. Use the proper kind of space (cheat sheet)
2. Use the proper accent character
3. Don't use hyphen for en dash
4. Don't use double hyphen for em dash
5. Don't use hyphen for minus
6. Don't use slash for division
7. Don't use neutral quote for smart quote
8. Undo italics for brackets and parenthesis
9. Don't use triple full stops for ellipsis
10. Don't use neutral quotes for primes
11. Use `utf-8` encode to avoid escaping
12. Always escape `<` with `&lt;`, `>` with `&gt;`, `"` with `&quot;`, `&` with `&amp;`

### Ligatures and abbreviations
1. Backword compatible CSS for enabling ligatures:
```css
body {
  font-feature-settings: "liga" 1;
}

@supports (font-variant-ligatures: common-ligatures) {
  body {
    font-feature-settings: normal; /* undo the legacy settings */
    font-variant-ligatures: common-ligatures;    
  }
}
```

