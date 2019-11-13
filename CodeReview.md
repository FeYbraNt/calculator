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