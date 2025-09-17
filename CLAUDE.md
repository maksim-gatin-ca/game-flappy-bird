# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a simple Flappy Bird game project designed for an 11-year-old child. The goal is to create a very simple, single-file HTML game that can run in a browser and be deployed to a web server.

## Requirements

Based on the project instructions:
1. Single file game (index.html)
2. Browser-based (HTML + JavaScript)
3. Very simple implementation
4. Mobile vertical layout view only (support small and larger screens)
5. Ready to deploy to remote web server
6. No build process or dependencies required

## Development Commands

This project requires no build, test, or compilation commands. It's a simple HTML file that can be:
- Opened directly in a browser for testing
- Deployed by copying the index.html file to any web server

## Architecture

- **Single file structure**: Everything contained in one index.html file with embedded CSS and JavaScript
- **No external dependencies**: Uses vanilla HTML, CSS, and JavaScript
- **Mobile-first design**: Optimized for vertical mobile screens with responsive canvas
- **Screen-based UI**: Multiple overlay screens (start, settings, game over) managed via display toggling
- **Configurable game system**: Settings object controls all game parameters with preset difficulty levels

### Game Structure

The game follows a simple state-based architecture:

1. **UI Screens**:
   - Start screen with game/settings buttons
   - Settings screen with configurable parameters and difficulty presets
   - Game canvas for active gameplay
   - Game over screen with restart option

2. **Game Settings System**:
   - `gameSettings` object contains all configurable parameters
   - Preset difficulty levels (Easy, Normal, Hard, Expert)
   - Real-time settings application without restart required
   - Manual parameter adjustment for fine-tuning

3. **Game Loop**:
   - Canvas-based rendering with `requestAnimationFrame`
   - Physics simulation for bird movement (gravity, velocity, jumping)
   - Collision detection between bird and pipes/boundaries
   - Dynamic pipe generation and cleanup

4. **Input Handling**:
   - Touch/click events for mobile-first design
   - Keyboard support (spacebar) for desktop testing
   - Unified jump function across all input methods

## Development Notes

- Game parameters are centralized in the `gameSettings` object for easy modification
- All game variables are updated via `updateGameVariables()` when settings change
- Canvas automatically resizes to fit container while maintaining aspect ratio
- Target audience is beginners, so code structure prioritizes readability over optimization
- Settings persist during game session but reset on page reload
- Mobile viewport optimization prevents zooming and ensures proper touch handling