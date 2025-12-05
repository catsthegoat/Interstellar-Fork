# Interstellar Web Proxy - Replit Configuration

## Project Overview
Interstellar is a web proxy application with a clean UI providing access to games and apps. The project serves over 8+ million users and features password protection, tab cloaking, themes, and various proxy capabilities.

## Recent Changes (December 5, 2025)
- Configured for Replit environment
- Updated server to bind to 0.0.0.0:5000 (required for Replit webview)
- Upgraded to Node.js 20 (from Node 16)
- **Password protection ENABLED** with username: interstellar, password: emma
- Removed "Request An App" and "Interstellar FAQ/Docs" from apps listing
- Configured autoscale deployment
- Updated .gitignore with proper Node.js patterns

## Project Architecture

### Technology Stack
- **Runtime**: Node.js 20
- **Framework**: Express.js
- **Proxy**: @nebula-services/bare-server-node
- **Package Manager**: npm (pnpm and bun also supported)

### Key Files
- `index.js` - Main server file, handles routing and proxy functionality
- `config.js` - Configuration for password protection
- `static/` - Frontend assets (HTML, CSS, JS, games, apps)
- `package.json` - Dependencies and scripts

### Server Configuration
- **Host**: 0.0.0.0 (binds to all interfaces for Replit)
- **Port**: 5000 (environment variable PORT or default 5000)
- **Bare Server**: Mounted at /ca/ endpoint
- **Static Files**: Served from /static directory

## Password Protection
Password protection is **enabled** (`challenge: true` in config.js).

Current credentials:
- Username: `interstellar`
- Password: `emma`

To disable password protection:
1. Edit `config.js` and set `challenge: false`
2. Restart the server

To add more users, edit the `users` object in `config.js` with username: password pairs.

## Deployment
- **Development**: Runs on port 5000 with `npm start`
- **Production**: Configured for autoscale deployment (runs on demand)
- **Port Binding**: Always uses 0.0.0.0 to work with Replit's proxy system

## Routes
- `/` - Home page
- `/a` - Games page
- `/b` - Apps page  
- `/c` - Settings page
- `/d` - Tabs page
- `/e/*` - External asset proxy (GitHub raw files)
- `/ca/` - Bare server proxy endpoint

## User Preferences
None documented yet.
