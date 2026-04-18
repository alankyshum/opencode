# Tailwind Theme Pitfalls

### OpenCode Custom Tailwind Class Names Require `-base` Suffix
**Source**: BLD-263 — OpenCode PR #22079 markdown preview toggle
**Date**: 2026-04-18
**Context**: When building a markdown preview toggle toolbar for OpenCode's file tabs, the initial implementation used standard-looking Tailwind class names (`bg-surface`, `text-text`, `border-border`) which rendered with transparent/missing styles because they don't exist in OpenCode's custom theme.
**Learning**: OpenCode's Tailwind theme uses `-base` suffixed semantic tokens. The correct classes are `bg-surface-base`, `text-text-base`, `border-border-base`, and `bg-surface-base-active`. Using the unsuffixed versions silently fails — no build error, just invisible/transparent rendering.
**Action**: When writing UI components for OpenCode, always use the `-base` suffix on semantic color tokens. If a component renders with missing styles, check for unsuffixed Tailwind class names first. Reference existing components in the codebase for correct class names.
**Tags**: tailwind, css, theming, opencode, ui, silent-failure
