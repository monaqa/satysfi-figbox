# satysfi-figbox

A SATySFi package that creates charts and places them in inappropriate positions in your document.

## Installation

Use [Satyrograpohs](https://github.com/na4zagin3/satyrographos).

```
opam install satysfi-figbox
satyrographos install
```

## Usage

Write the following code in your document file's preamble:

```
@require: figbox/figbox

open FigBox
```

## Example

```satysfi
+fig-on-right(
  let table =
    textbox { \easytable[l; c; r]{
      | a | b | c
      | d | e | f
      | g | h | i
      |}} |> hvmargin 5pt |> bgcolor (Color.gray 0.95)
  in

  vconcat ?:align-center [
    hconcat ?:align-center [
      table; gap 10pt; dummy-box 100pt 50pt;
    ];
    sep 20pt;
    hconcat ?:align-top [
      vconcat [
        dummy-box 80pt 70pt;
        gap 4pt;
        textbox ?:(set-font-size 8pt) {Dummy box!};
      ];
      gap 10pt; table;
    ];
  ] |> hvmargin 10pt |> frame 0.5pt Color.red
)<
  +p{
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
    Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
    Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
    Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  }
>
```

---

![example.png](https://user-images.githubusercontent.com/48883418/109374490-ee4a4780-78f8-11eb-951a-d6642a444e5c.png)

---
