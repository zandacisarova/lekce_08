# Tvořím web A–Z: lekce 8

Jaro 2021, Praha

<small>4. května 2021</small>

---

# Podklady

https://github.com/tvorimweb-2021-praha-jaro/lekce_08

---

# Dnešní cíle

- Naučit se CSS transformace a předchody (transitions)
- Seznámit se s tvorbou animací pomocí CSS

---

# Transform ≠ Transition

- transform = změna tvaru elementu
- transition = animace přechodu mezi stavy elementu

---

# Transform

CSS vlastnost `transform` s hodnotami například:

- `translate(x, y)`
- `scale(x, y)`
- `rotate(deg)`
- `skew(deg)`
- ...

---

# Transform - Příklad 1/2

```css
/* Zkosení */
.skew {
  transform: skew(-15deg);
}

/* Otočení */
.rotate {
  transform: rotate(-15deg);
}
```

note:

- jendotka deg = úhel ve stupních
- https://developer.mozilla.org/en-US/docs/Web/CSS/angle

---

# Transform - Příklad 2/2

```css
/* Posun */
.translate {
  transform: translate(0, 50%);
}

/* Změna velikosti */
.scale {
  transform: scale(1.5);
}
```

---

# Transition

CSS vlastnost `transition`:

- `<property> <duration> <easing> <delay>`
- `property`: vlastnost, na kterou se `transition` vstahuje, prázdná znamená všechny
- `duration`: délka přechodu (v ms)
- `easing`: křivka hodnot v čase
- `delay`: zpoždění animace (v ms)

---

# Transition - Příklad

```css
button {
  background-color: blue;
  transition: 300ms;
}

button:hover {
  background-color: red;
}
```

---

# Transition - Příklad jednotlive vlatnosti 1/2

```css
div {
  /* co se bude animovat */
  transition-property: margin, height, ...;

  /* jakým způsobem se bude animovat */
  transition-timing-function: ease | linear |...;
}
```

note:

- https://css-tricks.com/almanac/properties/t/transition/

---

# Transition - Příklad jednotlive vlatnosti 2/2

```css
div {
  /* jak dlouho bude animace probíhat */
  transition-duration: 500ms | 0.5s;

  /* jak dlouho se počká než začne průběh */
  transition-delay: 500ms | 0.5s;
}
```

---

# Transition - Zkrácený zápis

```css
element {
  transition: ([transition-property]) [transition-duration]
    ([transition-timing-function]) ([transition-delay]);
}
```

---

# Transition - Zkrácený zápis - Příklad

```css
div {
  margin-top: 100px;
  transition: margin-top 300ms ease 1s;
}

div:hover {
  margin-top: 200px;
}
```

note:

https://css-tricks.com/almanac/properties/t/transition-timing-function/

---

# Animace

- CSS vlastnost `animation`:
  - `nazev-animace delka [pocet opakovani] [smer] [fillmode]`
  - `animation-iteration-count` - počet opakování nebo `infinite`
  - `animation-direction` - `normal`, `reverse`, `alternate`
  - `animation-fill-mode` - `none`, `forwards`, `backwards`, ...
  - `@keyframes nazev-animace`
    - `from { vychozi stav }`
    - `to { cilovy stav }`
    - `X% { stav v daném procentu animace }`

---

# Animace - Příklad

```css
.icon {
  animation-name: spin; /* název shodný s názvem za @keyframes */
  animation-duration: 2s; /* trvání animace */
  animation-iteration-count: infinite; /* počet opakování */
  animation-timing-function: linear; /* průběh animace */
}

@keyframes spin {
  from {
    /* výchozí stav prvku */
  }

  to {
    /* koncový stav prvku */
  }
}
```

---

# Povinný domácí úkol

- Zadaný v classrooms
- Ukážeme si co je třeba

![Super appka](https://raw.githubusercontent.com/TvorimWeb-2018-Praha/projekt3-superappka/master/vysledek.png)
