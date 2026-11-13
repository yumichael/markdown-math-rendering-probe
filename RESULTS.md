# Observed rendering results

Checked November 12, 2026 against [README.md](README.md), initially published in commit f2e53c1. GitHub was inspected visually in Chrome on the public rendered file, including its generated math elements. The local comparison used the Markdown parser and math plugin bundled with installed VS Code 1.142.0, with KaTeX 0.16.21, to render the same Markdown source. The VS Code column records generated HTML checks; it is not a claim about every extension, notebook renderer, or editor mode.

| Test in README | GitHub rendered file | Installed VS Code parser and math plugin |
| --- | --- | --- |
| Inline math in prose | Renders | Renders |
| Inline math in level-two and level-three headings | Renders | Renders |
| Inline math in unordered and nested unordered lists | Renders | Renders |
| Inline math in ordered lists | Renders | Renders |
| Inline math in table headers and body cells | Renders | Renders |
| Inline math in a blockquote | Renders | Renders |
| Inline math inside bold text | Renders | Renders |
| Inline math inside the tested italic span | Remains literal | Renders |
| Top-level display equation | Renders | Renders |
| Display equation indented inside the tested list item | Remains literal | Renders |
| Operator-name command | Rejected: operatorname macro is not allowed | Renders |
| Roman-text command and the tested congruence | Render correctly | Render correctly |
| Aligned equations and matrix with standard double-backslash row separators | Row separators are altered; output is incorrect | Render correctly |
| Dollar-delimited inline math | Renders | Renders |
| GitHub backtick-in-dollar alternative | Renders | Backticks become formula content; not equivalent |
| Parenthesis and bracket delimiters without dollar signs | Remain ordinary text | Remain ordinary text |
| Math syntax inside a code span | Remains literal, as expected | Remains literal, as expected |
| Unescaped pipe inside a table formula | Table cell is split; formula is broken | Table cell is split; formula is broken |
| Absolute-value and divisibility commands avoiding a raw pipe | Render correctly | Render correctly |

These observations disprove a blanket restriction on inline math in headings, tables, or lists. They also show that success in VS Code does not establish GitHub compatibility. This finite probe is not an exhaustive catalogue of supported LaTeX commands or Markdown nesting combinations.

For shared documents, dollar-delimited inline math is usable in prose, lists, and table cells. Use commands such as `\lvert` and `\mid` to avoid the Markdown table separator. Plain-text headings remain a reasonable navigation convention, because anchors and outlines have their own handling of mathematical source. Keep complicated equations outside list indentation unless that exact layout has been checked on both renderers. Check both the Markdown structure and the mathematical output, including row breaks and scripts.

See the official [GitHub mathematical-expression documentation](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions), [VS Code Markdown documentation](https://code.visualstudio.com/docs/languages/markdown#_math-formula-rendering), and [VS Code math plugin](https://github.com/microsoft/vscode-markdown-it-katex). The current GitHub rendering observations above take precedence over assuming that every MathJax or LaTeX macro is available.
