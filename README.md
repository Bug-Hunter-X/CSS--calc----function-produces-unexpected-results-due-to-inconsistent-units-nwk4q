# CSS `calc()` function produces unexpected results due to inconsistent units

This repository demonstrates a common issue encountered when using the CSS `calc()` function: unexpected results due to unit inconsistencies.

## Bug Description

The `calc()` function is powerful for dynamic calculations within CSS. However, if units are not consistent, it can lead to incorrect results.

## Example

Consider the following CSS:

```css
/* bug.css */
.container {
  width: 500px;
}

.element {
  width: calc(100% - 50px);
}
```

In this case, one might expect `.element` to have a width of 450px. However, the result may vary depending on the browser's interpretation of the mixed units (percentage and pixels). 

## Solution

The best practice is to ensure consistent units within the `calc()` function.  Preferably, use the same unit throughout the calculation, or ensure proper unit conversion.

```css
/* bugSolution.css */
.container {
  width: 500px;
}

.element {
  width: calc(500px - 50px); /* Consistent units: pixels */
  /* Or use percentage consistently if possible: */
  /*width: calc(100% - 10%); /* This would require knowing the context */
}
```