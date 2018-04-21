```css
/* ligatures: common, discretionary, historical */
.legacy {
  font-feature-settings: "liga" 1, "dlig" 1, "hist" 1;
}

.new {
  font-variant-ligatures: common-ligatures, discretionary-ligatures, historical-ligatures;
}

/* old-style numerals */
.legacy {
  font-feature-settings: "onum" 1;
}

/* small caps */
.legacy {
  font-feature-settings: "smcp" 1;
}

.new {
  font-variant-caps: small-caps;
}

.legacy {
  text-transform: lowercase; /* in case c2sc feature isn't available */
  font-feature-settings: "smcp" 1, "c2sc" 1;
}

.new {
  font-variant-caps: all-small-caps;
}
```
