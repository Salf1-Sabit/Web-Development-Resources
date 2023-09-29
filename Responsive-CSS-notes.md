## Mobile first or Desktop first?

Answer: Mobile. Because if we take a closer look, our HTML stays responsive by default and we should take advantage of that. <br/>
Then, we can just add min-width media queries with less code. And just add the layouts for the desktop design.

```css
@media screen and (min-width: 900px) {
  /* Your new code goes here for large devices */
}
```

## EM v/s REM

#### EM: <br/>

Always uses it's parent's units as 1em. Better to use for font-size and margin/padding.

```css
.parent {
    font-size: 2em;
}
.child {
    font-size: 4em: /* 4em x 2em = 8em */
}
```

If-applied to margin and padding then, the font-size of the current element is considered as 1em (useful for buttons).

```css
.div {
  font-size: 2em;
  margin: 3em; /* 3em x 2em = 6em
}
```

#### REM: <br/>

Always uses root's units as 1rem.

```css
.child {
  font-size: 2rem; /* 2rem x 16px = 32px */
}
```

Which is 16px by default. And can be change in this way:

```css
html {
  font-size: 20px; /* By-default 16px */
}
```
