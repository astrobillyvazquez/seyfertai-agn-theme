# Changelog

## [1.1.1] — 2026-04-17

### Added — full git / problem / test signal coverage across all three variants

- **Testing API tokens** (19 tokens): `testing.iconPassed`, `iconFailed`, `iconErrored`, `iconSkipped`, `iconQueued`, `iconUnset`, `runAction`, `peekBorder`, `peekHeaderBackground`, `message.error.decorationForeground`, `message.error.lineBackground`, `message.info.decorationForeground`, plus full coverage/uncovered decoration tokens (`coveredBackground`, `coveredBorder`, `coveredGutterBackground`, `uncoveredBackground`, `uncoveredBorder`, `uncoveredGutterBackground`). Test results now carry a clear visual language: moss = passed, coral = failed, pink = errored (runtime), dust-gray = skipped, indigo = queued.
- **Lightbulb (code action) tokens**: `editorLightBulb.foreground` (AGN-gold — consequential), `editorLightBulbAutoFix.foreground` (moss — safe auto-fix), `editorLightBulbAi.foreground` (indigo-bright — AI surface).
- **Inlay hint tokens** (6 tokens): `editorInlayHint.foreground` / `.background`, `.typeForeground` / `.typeBackground`, `.parameterForeground` / `.parameterBackground`. Type hints get cyan, parameter hints get starlight — matching the in-editor syntax scopes they annotate.
- **Ghost text (AI suggestion / Copilot inline) tokens**: `editorGhostText.foreground` / `.background` / `.border`. Dimmed indigo-void — clearly an AI surface, recedes from user-authored code.
- **Error / Warning / Info / Hint borders**: explicit transparent border values so VS Code falls back to squiggles (not boxes) for diagnostics.
- **Editor gutter comment markers**: `editorGutter.commentRangeForeground`, `commentGlyphForeground`, `commentUnresolvedGlyphForeground` — PR / inline review signals use the theme palette instead of VS Code defaults.
- **Minimap info highlight**: `minimap.infoHighlight` — completes the minimap stripe triplet (error / warning / info) across all three variants.

### Design system notes

- **Indigo is now the "AI surface" marker.** `editorLightBulbAi.foreground`, ghost text ambient, and test `runAction` all use the indigo-bright family, giving AI touchpoints a consistent visual language distinct from user-authored code and gold-sacred strings.
- **Hybrid stoplight strategy.** Universal green/red signaling (git added/deleted, test pass/fail) uses the Seyfert palette's moss and coral — close enough to stoplight convention for instant recognition, but palette-coherent. Other decorative greens/reds throughout the theme keep the original Seyfert hues.

## [1.1.0] — 2026-04-16

### Added
- **Seyfert AGN — Soft Contrast** — a third variant designed for relaxed, reduced-eye-strain coding. The full void ramp is lifted by ~2 tonal stops so the ground reads as a lifted grey-indigo rather than near-black. Accent colors are desaturated ~15% to keep hue identity while cutting chroma (the typical eye-strain culprit). Foreground is warmed and dimmed from #E5E9F2 to #DDE2ED.
- **High-visibility scrollbars** on the Soft Contrast variant — scrollbar thumb is now unmistakable (indigo-light @ 72% opacity idle, indigo-bright @ 88% on hover, AGN-gold fully opaque on drag).
- Lifted selection, cursor, line highlight, and indent-guide contrast on Soft Contrast for readability on the lifted ground.

## [1.0.0] — 2026-04-16

### Added
- **Seyfert AGN Dark** — primary color theme, Monokai architecture rebuilt on the Seyfert AI space-indigo palette.
- **Seyfert AGN — High Contrast** — contrast-lifted variant for presentations, code review, and bright environments.
- **Accretion Icons** — a full file + folder icon theme (100+ glyphs) with monochrome indigo base and strategic gold/pink/cyan accents for config, test, and type files.
- Semantic token colors for modern language servers (TypeScript, Rust, Go, Python, Ruby).
- Bracket pair colorization (6-stop palette: indigo → indigo-light → cyan → violet → gold → pink).
- Full terminal ANSI 16 palette.
- Tasteful italics on comments, parameters, `this`/`self`, and storage modifiers.
