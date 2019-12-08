# Learn how to use the slot method in vue.js framework.

## slot :
  - Slots (不具名插槽)
  - Named Slots (具名插槽)
  - Scoped Slots (作用域插槽)

## Exercise 1: slot-test component

Through the slot method to add additional content in slot-test component.

key point:
  1. A `slot` outlet without name implicitly has the name `default`, so it will render those contents which is unspecified name 
  不具名的 `slot`， `name` 預設值為 `default` ，代表會渲染那些沒有特定名稱的內容

  2. If we give `slot` a default content (Here is `This is a content`), it will render `This is a content` when slot get nothing to show. 
  如果我們有提供預設的內容給 `slot`，當 `slot` 沒有取得任何要被插入的內容時，就會使用預設值的內容

## Exercise 2: submit-button

Through the slot method to replace contents, and we can reuse this component to custom different content.

key point:
  1. We can use the `slot` method to reuse the button which has the same css style and structure, but different name.
  我們可以透過 `slot` 方法來重複使用一個僅僅是名稱不同，而樣式與結構都相同的按鈕。

## Exercise 3: named-slot

Through the `template`, slot or v-slot (or shorthand #), we can insert content into specify area.

key point:
  1. Use `slot` and give name `header` in named-slot component, it present we want to insert contents into header area, and we set contents in `<template slot="header">`
  透過 `slot` 並給予名稱 `section`，並在 `template` 中放入要插入的內容，就可以讓我們將內容放入到 `section`的區塊，
  2. Use `slot` and give name `section` in named-slot component, it present we want to insert contents into section area,and we set contents in `<template v-slot="section">`
  透過 `slot` 並給予名稱 `section`，並在 `<template v-slot="section">` 中放入要插入的內容，就可以讓我們將內容放入到 `section`的區塊
  3. Use `slot` and give name `footer` in named-slot component, it present we want to insert contents into footer area, and we set contents in `<template #footer>` (Here use shorthand `#`)
  透過 `slot` 並給予名稱 `footer`，並在 `<template  #footer>` 中放入要插入的內容，就可以讓我們將內容放入到 `footer` 的區塊

  p.s.
    1. `v-slot` support after version 2.6.0, and only be added to a `<template>`
    2. `slot`  support before version 2.6.0 

## Exercise 4: scoped-slot

Scoped Slots let us to use data which is in the children component, and use it in parent component.

有時候我們需要拿取子元件中的資料來替換當前子元件中的某個資料的值時

作用域插槽允許我們拿取子元件中的的資料來父元件中使用。

key point:

  Target: use children component's data to replace text in parent component.

  Step1: (In custom component tag) use slot and slot-scope or v-slot
    1. use slot and slot-scope
    2. use v-slot 
  Step2: (In children component) bind the data which we want to use in children component.

  目標: 使用子元件中的資料來將 `text` 的值 `This is a text.` 替換成 `text2` 的值 `This is a text2.`

  步驟1: 在自定義標籤中選擇使用 slot and slot-scope 或者 v-slot 
  步驟2: 在子元件中綁定想要讓父元件使用的資料

## Exercise 5: destructuring slot props 

Here we use scoped-slot component to show how to destructuring slot props

這邊我們同樣使用 scoped-slot 元件來看看如何解構插槽

key point: 

  1. use mustache `{props1, props2}` in parent component, and children component do not to change.

  在父元件使用 `{}` 將所有綁定的的屬性解構，而子元件不需要有任何改變



tips: 

  1. First, we can use `<slot></slot>` to let us inert contents in custom component.
    第一，我們可以透過 `<slot></slot>` 來將額外要插入的內容放到自定義的元件裡面
  2. Second, we set contents in custom component tag, such as `named-slot`
    第二，我們可在自定義元件的標籤中放入內容
