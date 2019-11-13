# Code Review

## Good/Bad practices

- First things come first: Use ES6, nowadays all browsers are compatible with it and it improves a lot your code.
- Better use a CSS-Precompiler (i.e. SASS/Less) for styling.
- I'd have used a small UI library like Vue to make easier maintenance and improve compatibility.
- Remove trailing zeros just adding `resultNum = new Number(resultNum.toString())` 

## Fixes

- Nested classes in CSS: `&::before, &::after { ... }` should be `calculator::before, calculator::after` and outside `.calculator`
- Number buttons '3' and '0' were reversed: `<button id="btn" class="num" data-num="0">3</button>` should be `<button id="btn" class="num" data-num="0">0</button>` and so on.
- Perform operation was reversed: `resultNum = oldNum - theNum;` should be `resultNum = oldNum + theNum;` and so on.
- Avoid non-numbered values (zero by default): `oldNum = parseFloat(oldNum) || 0` and `theNum = parseFloat(theNum) || 0`

## New features

- Multiply
- Divison

`package.json` version has been increased to 1.3.0, this is because we always increase on this order:

- Left number: Release version
- Middle number: Feature version
- Right number: Fixes version

As we have made some fixes first we increase right number first (1.2.3) but later we added new feature so right number resets to zero and middle number increases (1.3.0).

## Test automation

- Unit tests with javascript libraries like **Jasmine**.
- Tests focusing on functionality esentially: do all operations and try to play with them

## UI/UX design

- Add HTML responsive viewport `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- Styles improvements to make easier to distinguish all parts of the app: 
  - Add box-sizing CSS rule to add default box sizes
  - Add div boxes 
  - Add borders