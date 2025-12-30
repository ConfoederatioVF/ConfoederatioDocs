The following example creates a sample FlexInterface window in [[Vercengen]] with automatically-resizing partitions. A FlexInterface can also generally be achieved by setting the `.options.type` parameter of a `veInterface` constructor to 'flex'.

```js
myFlexLayout = veWindow(new ve.FlexInterface({
  type: "vertical",
  // Child 1: Flex 1 (Top)
  flex_1: veHTML(
    `<div style="background-color: blueviolet; color: white; height: 100%; padding: 10px;">Flex 1</div>`,
  ),

  // Child 2: The Horizontal row (Bottom)
  main_row: {
    type: "horizontal",

    // Sub-child 1: Flex 2 (The section with textareas)
    flex_2: veHTML(`
      <section style="background-color: aqua; padding: 20px; height: 100%; box-sizing: border-box;">
        <div>
          <label for="CursorCoor" style="display: block; font-weight: bold;">showCursorCoor: </label>
          <textarea id="CursorCoor" rows="6" style="width: 100%;" wrap="soft" readonly></textarea>
        </div>
        <br />
        <div>
          <label for="boxInfo" style="display: block; font-weight: bold;">showBoxInfo: </label>
          <textarea id="boxInfo" rows="6" style="width: 100%;" wrap="soft" readonly></textarea>
        </div>
      </section>
    `),

    // Sub-child 2: The Vertical stack on the right
    right_stack: {
      type: "vertical",

      // Inner-child 1: Flex 3
      flex_3: veHTML(
        `<div style="background: pink; height: 100%; padding: 10px;">Flex 3</div>`,
      ),

      // Inner-child 2: The nested horizontal row at the very bottom right
      bottom_right_row: {
        type: "horizontal",

        flex_4: veHTML(
          `<div style="background: green; color: white; height: 100%; padding: 10px;">Flex 4</div>`,
        ),

        flex_5: veHTML(
          `<div style="height: 100%; padding: 10px; border: 1px solid #ccc;">Flex 5</div>`,
        ),

        // If you want to replicate the 'no-resizer' between 5 and 6 specifically, 
        // you would normally group them, but the current generateHTMLRecursively 
        // adds resizers based on index.
        flex_6: veHTML(
          `<div style="background: darkorange; height: 100%; padding: 10px;">Flex 6</div>`,
        ),
      },
    },
  },
}));
```