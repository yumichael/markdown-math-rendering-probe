# Markdown math rendering probe

Synthetic examples for comparing GitHub's rendered Markdown files with VS Code's built-in Markdown preview. Created November 12, 2026. This is a rendering test, not a claim that every LaTeX command is supported.

## Heading with inline math $x^2+\alpha$

### Heading with subscripts $a_n+b_n$

Prose: $x^2+\alpha$. Subscripts: $a_n+b_n$. Bold text: **formula $x^2+\alpha$**. Italic text: *formula $x^2+\alpha$*.

- Unordered list: $x^2+\alpha$.
  - Nested unordered list: $a_n+b_n$.

1. Ordered list: $x^2+\alpha$.
2. Another ordered item: $\nu_2(p)$.

> Blockquote: $x^2+\alpha$.

| Context | Formula $a_n$ |
| --- | --- |
| Table body | $x^2+\alpha$ |
| Subscripts | $a_n+b_n$ |
| Absolute value without literal pipe | $\lvert x\rvert$ |
| Divisibility without literal pipe | $a\mid b$ |

## Display math

$$
\sum_{j=1}^{n}j=\frac{n(n+1)}{2}
$$

- Display math inside a list, indented to belong to the item:

  $$
  x^2+\alpha
  $$

## Representative commands and environments

Operator name: $\operatorname{ord}(x)$. Roman operator: $\mathrm{ord}(x)$. Congruence: $H(2N-z)\equiv H(z)\pmod M$.

$$
\begin{aligned}a+b&=c\\d+e&=f\end{aligned}
$$

$$
\begin{pmatrix}a&b\\c&d\end{pmatrix}
$$

## Delimiter probes

Dollar-delimited positive control: $x^2+\alpha$.

Backtick-in-dollar GitHub alternative: $`x^2+\alpha`$.

Parenthesis delimiters, for comparison: \(x^2+\alpha\).

Bracket delimiters, for comparison:

\[
x^2+\alpha
\]

Code span, which should remain literal: `$x^2+\alpha$`.

## Intentional table-pipe conflict

This last example deliberately contains an unescaped literal pipe inside math. Compare it with the `\lvert` example above. A table parser may split the formula into extra cells before math rendering.

| Context | Formula |
| --- | --- |
| Literal pipe | $|x|$ |
