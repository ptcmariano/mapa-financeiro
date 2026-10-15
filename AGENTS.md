# Repository Guidelines

## Project Structure & Module Organization

This is a standalone, browser-based “Roda da Vida” self-assessment with Brazilian Portuguese content.

- `roda-financeira.html` contains the page markup, question data, inline JavaScript, result tables, and CSV export. The questionnaire covers 13 areas with five questions each.
- `style.css` contains shared styles, theme variables, responsive rules, and print styles.

There are currently no separate source, test, or asset directories, package manifests, or backend services. Keep additions consistent with this small static structure.

## Build, Test, and Development Commands

No installation or build step is required.

- `Start-Process .\roda-financeira.html` opens the page in the default browser on Windows.
- `python -m http.server 8000` serves the current directory if Python is installed. Visit `http://localhost:8000/roda-financeira.html`; there is no `index.html` entry point.

Reload the browser after editing either file.

## Coding Style & Naming Conventions

Use two-space indentation in HTML, CSS, and JavaScript. Prefer `const` for fixed bindings and `let` for changing state. Follow existing camelCase JavaScript names such as `readValue` and `showResult`, and hyphenated CSS classes such as `.progress-row`.

Reuse CSS custom properties declared in `:root`. Keep interface copy in Brazilian Portuguese and preserve UTF-8 accents and emoji. Escape user-entered text before inserting it into HTML, following the existing `esc` helper. No formatter or linter is configured.

## Testing Guidelines

No automated test framework or coverage threshold is configured. For each behavior change, manually check:

- Start, required-answer validation, back navigation, and completion of all 65 questions.
- Scores of both 0 and 10, text answers containing quotes or angle brackets, and priority choices.
- Result tables, action-plan fields, restart, print preview, and downloaded CSV contents.
- Desktop and narrow mobile layouts, keyboard navigation, and browser-console errors.

Check relative links: the close control currently references an absent `index.html`.

## Commit & Pull Request Guidelines

This checkout has no Git metadata, so existing commit conventions cannot be verified. When contributing through Git, use concise imperative subjects, for example `Fix zero-score selection`.

Describe the change and manual checks in pull requests. Link relevant issues and include desktop/mobile screenshots for visual changes.
