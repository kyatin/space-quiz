# Copilot Instructions

Single-file static web app: `index.html` contains all HTML, CSS, and JS. There is no build system, package manager, tests, or linter. Run it by opening `index.html` in a browser (or `python3 -m http.server`).

## Architecture

- **Data**: `Q` is an array of tuples `[question, [options…], correctIndex]`. Add or edit questions there.
- **State**: module-level `i` (current question), `score`, `locked` (blocks double answers).
- **Flow**: `render()` draws question `i` → `pick(k)` grades and reveals the Next button → `#next` click advances or calls `finish()` → `#again` resets state and re-renders.
- **UI**: DOM is updated imperatively via `$ = id => getElementById`; the quiz card (`#quiz`) and results card (`#result`) are toggled with the `hidden` attribute.

## Conventions

- Keep the score thresholds in `finish()` and the hardcoded `10` (perfect-score check, `aria-valuemax`, initial "Question 1 of 10") in sync with `Q.length` if the question count changes.
- Theming uses CSS variables in `:root`, with a `prefers-color-scheme: dark` override; use the variables rather than hardcoded colors.
- Accessibility is deliberate: focus moves to the first option/Next/Play again button, `#fb` is `aria-live`, the progress bar has `role="progressbar"`, and `prefers-reduced-motion` disables animations. Preserve these when changing UI.
- Stay dependency-free and single-file; compact, minified-style code is the existing style.
