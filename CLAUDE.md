# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a documentation repository for the **DSFR (Système de Design de l'État Français)** - the official design system framework for French government websites and applications. The repository contains comprehensive reference guides for implementing DSFR-compliant interfaces.

## Repository Structure

- `/DSFR/` - All DSFR documentation files
  - `DSFR-FONDAMENTAUX*.md` - Core principles, colors, spacing (8-point grid), typography, and grid system
  - `DSFR-PALETTE.md` - Official color palette with decision tokens
  - `DSFR-TYPOGRAPHIE.md` - Typography specifications (Marianne® and Spectral fonts only)
  - `DSFR-FONDAMENTAUX-ICONES.md` - Icon usage guidelines (Remix Icons)
  - `DSFR-COMPOSANT-*.md` - Individual component documentation (buttons, forms, modals, tables, etc.)

## MCP Servers

The project has configured MCP servers (`.mcp.json`):
- **Grist**: Connection to Grist API at `grist.numerique.gouv.fr` for data management
- **Context7**: Documentation context service

## Key DSFR Principles

When working with this documentation or generating DSFR-compliant code:

1. **All or Nothing**: DSFR implementation must be complete - no partial implementations or modifications to official components
2. **White Background Required**: Legal requirement (Law of July 29, 1881) - default background must be white
3. **Decision Tokens Only**: Never use color option values directly - always use decision tokens (e.g., `$background-default-grey`)
4. **Authorized Fonts Only**: Marianne® (body text) and Spectral (alternate titles) - no other fonts permitted
5. **CSS Load Order Critical**: core → utility → icons → scheme → components
6. **Theme Script Before CSS**: Dark mode script must load before any CSS
7. **Accessible Buttons**: All buttons must have visible text labels (not icon-only)
8. **No Native Alerts**: Use `fr-alert` component instead of `alert()`, `confirm()`, `prompt()`
9. **Grid Hierarchy**: Always follow `fr-container` → `fr-grid-row` → `fr-col-*`
10. **RGAA 4.1 Compliance**: All DSFR components guarantee 100% accessibility compliance

## DSFR Version

Current documented version: **1.14**
Official site: https://www.systeme-de-design.gouv.fr/
