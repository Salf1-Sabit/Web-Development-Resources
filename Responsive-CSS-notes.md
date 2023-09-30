## Useful flexbox patterns

[Click here to show the PDF](https://drive.google.com/file/d/1vj-TcRh6YQe9Qd2xlMumffWb2XsiwOuQ/view?usp=sharing)

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

Always uses it's parent's units as 1em.

```css
.parent {
    font-size: 2em;
}
.child {
    font-size: 4em: /* 4em x 2em = 8em */
}
```

Better to use for margin/padding. But, not for font-sizes. Because font-sizes will consider it's parent's size. And the units will keep multiplying. <br/>
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

## Flex-Basis

After applying {display: flex} to any element. The direct children becomes of different sizes. To avoid that, { flex-basis: 100% } can be applied on all of it's children. This properpty says that, all of the children must be of same size.

```css
.parent {
  display: flex;
}
.parent > * {
  flex-basis: 100%; /* targeting all the direct children and applying the property to all of them. */
}
```

## min(), max() and clamp()

#### min() and max()

When using min() or max(), to get the full potential of responsiveness, it's better to use a fixed unit and a relative unit as arguments.

```css
.content {
  width: min(500px, 70%);
}
```

#### clamp(min_size, ideal_size, max_size)

Receives 3 arguments. Middle argument should always be relative unit. Which helps with responsiveness. Clamp is good for "font-size". <br/>
Effect: locked in at a minimum size --> starts inceasing --> locked in at a maximum size.

```css
.content {
  font-size: clamp(2rem, 5vw, 5rem);
}
```
