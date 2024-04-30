---
slide: 1
layout: cover
---

# Markdown Syntax

You can use Markdown, HTML and Vue Components. And style it with UnoCSS.

Use `---` on a new line to separate your slides.

---
slide: 2
layout: center
background: './images/download.png' # Not working
---

# Code Blocks

We can use Markdown to highlight our code: ` ```ts 'your code here' ``` `

## Line Highlighting

We will use: `ts {2, 3}`

```ts {2,3}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

To see the lines of code and start to count from x: `{lines:true, startLine:5}`

```ts {6,7}{lines:true,startLine:5}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

---
slide: 3
layout: cover
---

## Line Highlighting

To change the highlight in multiple clicks: `{2-3|5|all}`. You can use {at:4} to delay the start until the 4th click.

```ts {2-3|5|all}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

You can hide blocks of code: `{hide|none|all}`

```ts {hide|none|all}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
```

If the code doesn't fit: `{maxHeight:'90px'}`

```ts {2|3|7|12}{maxHeight:'90px'}
function add(
  a: Ref<number> | number,
  b: Ref<number> | number
) {
  return computed(() => unref(a) + unref(b))
}
/// ...as many lines as you want
const c = add(1, 2)
```

---
slide: 4
layout: cover
---

# TwoSlash Integration

TwoSlash is a powerful tool for rendering TypeScript/JS code blocks with type information on hover or inlined. You can use it by writing this alongside ts: ` ```ts twoslash``` `

```ts twoslash
import { ref } from 'vue'

const count = ref(0)
//            ^?
```

---
slide: 5
layout: cover
---

# Shiki Magic Move

We can use Shiki Magic Move by placing your code blocks inside here: ` ````md magic-move 'first block' 'second block' ```` `

````md magic-move
```js {*|1|2-5}
let count = 1
function add() {
  count++
}
```

Non-code blocks in between as ignored, you can put some comments.

```js
let count = 1
const add = () => count += 1
```
````

---
slide: 6
layout: cover
---

# Monaco Editor

Simply by adding `{monaco}` yo will be able to edit the code block.

```ts {monaco}
console.log('HelloWorld')
```
<br>

## Monaco Diff

You can see the difference between two code blocks using `{monaco-diff}` and using `~~~` to separate the blocks.

```ts {monaco-diff}
console.log('Original text')
~~~
console.log('Modified text')
```

---
slide: 7
layout: cover
---

## Monaco Runner

If you want to run code and see the result, add `{monaco-run}`. By default it will automatically run the code. Use `{autorun:false}` if you want to always explicitly trigger the run.

```ts {monaco-run} {autorun:false}
function distance(x: number, y: number) {
  return Math.sqrt(x ** 2 + y ** 2)
}
console.log(distance(3, 4))
```

You can show the output in a certain click using this prop: `{showOutputAt:'+1'}`

```ts {monaco-run} {showOutputAt:'+1'}
console.log('Shown after 1 click')
```

---
slide: 8
layout: cover
---

# Embedded Styles
