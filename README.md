# GTA 5 2D Clone - Coding Overview

This project is a 2D top-down open-world game built using a modern full-stack JavaScript architecture.

## Architecture

### 1. Frontend Game Engine (`client/src/game/engine.ts`)
The core of the game is a high-performance Canvas-based engine. It uses a standard game loop:
- **Input Handling**: Captures keyboard (WASD) and mouse events.
- **Update Phase**: Calculates physics, collisions, and AI movements.
- **Render Phase**: Draws the city, vehicles, and entities to the screen.

### 2. State Management (`client/src/hooks/use-game.ts`)
Uses **TanStack Query** to sync game progress with the backend. It handles:
- Loading the player's position, cash, and health.
- Saving state periodically or on significant events.
- Fetching world entities like vehicles and missions.

### 3. Shared Schema (`shared/schema.ts`)
Defines the "Source of Truth" for data using **Drizzle ORM**:
- **Users**: Player stats and current world position.
- **Vehicles**: Spawn points and properties of drivable cars.
- **Missions**: Objectives and rewards.

### 4. Backend (`server/`)
A thin **Express** server providing:
- **API Routes (`routes.ts`)**: Endpoints for saving/loading and mission management.
- **Storage Layer (`storage.ts`)**: Abstracted database operations using a repository pattern.
- **Database (`db.ts`)**: PostgreSQL connection managed via Drizzle.

## Key Technologies
- **React**: For the HUD and menu overlays.
- **HTML5 Canvas**: For the 2D game world rendering.
- **Drizzle ORM**: For type-safe database interactions.
- **Tailwind CSS**: For the gritty, urban UI design.
- **Wouter**: For lightweight client-side routing.
