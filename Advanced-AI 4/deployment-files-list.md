
# Files Required for Discord AI Bot Deployment

## Core Configuration Files

### package.json
Contains all dependencies and scripts needed for the project.

### tsconfig.json  
TypeScript configuration for the entire project.

### .env (CREATE THIS FILE)
```
DISCORD_TOKEN=your_discord_bot_token
OPENAI_API_KEY=your_openai_api_key
NODE_ENV=production
DATABASE_URL=your_database_url
```

### drizzle.config.ts
Database configuration for Drizzle ORM.

## Server Files (server/)

### server/index.ts
Main Express server entry point.

### server/routes.ts
API endpoints for the web dashboard.

### server/db.ts
Database schema and connection setup.

### server/storage.ts
Database operations and queries.

### server/discord/bot.ts
Main Discord bot client and event handlers.

### server/discord/handler.ts
Message processing and AI response logic.

### server/discord/slashCommands.ts
Slash command definitions and handlers.

### server/openai/client.ts
OpenAI API integration.

## Client Files (client/)

### client/index.html
Main HTML entry point for the dashboard.

### client/src/main.tsx
React application entry point.

### client/src/App.tsx
Main React application component.

### client/src/index.css
Global styles and Discord theme colors.

### client/src/pages/dashboard.tsx
Web dashboard interface.

### client/src/pages/not-found.tsx
404 error page.

### client/src/lib/utils.ts
Utility functions.

### client/src/lib/queryClient.ts
React Query client configuration.

### client/src/hooks/use-toast.ts
Toast notification hook.

### client/src/hooks/use-mobile.tsx
Mobile detection hook.

### All UI Components (client/src/components/ui/)
- accordion.tsx
- alert-dialog.tsx
- alert.tsx
- aspect-ratio.tsx
- avatar.tsx
- badge.tsx
- breadcrumb.tsx
- button.tsx
- calendar.tsx
- card.tsx
- carousel.tsx
- chart.tsx
- checkbox.tsx
- collapsible.tsx
- command.tsx
- context-menu.tsx
- dialog.tsx
- drawer.tsx
- dropdown-menu.tsx
- form.tsx
- hover-card.tsx
- input-otp.tsx
- input.tsx
- label.tsx
- menubar.tsx
- navigation-menu.tsx
- pagination.tsx
- popover.tsx
- progress.tsx
- radio-group.tsx
- resizable.tsx
- scroll-area.tsx
- select.tsx
- separator.tsx
- sheet.tsx
- sidebar.tsx
- skeleton.tsx
- slider.tsx
- switch.tsx
- table.tsx
- tabs.tsx
- textarea.tsx
- toast.tsx
- toaster.tsx
- toggle-group.tsx
- toggle.tsx
- tooltip.tsx

## Shared Files

### shared/schema.ts
Shared TypeScript types and schemas.

## Styling Configuration

### tailwind.config.ts
Tailwind CSS configuration with Discord theme.

### postcss.config.js
PostCSS configuration.

### components.json
Shadcn/ui components configuration.

## Additional Files Needed

### .gitignore
```
node_modules/
dist/
build/
.env
.env.local
.env.production
*.log
.DS_Store
.vscode/
.idea/
coverage/
*.tsbuildinfo
```

### Procfile (for Render deployment)
```
web: npm run start
```

### render.yaml (Render configuration)
```yaml
services:
  - type: web
    name: discord-ai-bot
    env: node
    buildCommand: npm install && npm run build
    startCommand: npm run start
    envVars:
      - key: NODE_ENV
        value: production
      - key: DISCORD_TOKEN
        sync: false
      - key: OPENAI_API_KEY
        sync: false
```

## Database Setup (if using external DB)
Create a SQLite database or configure PostgreSQL connection in your deployment environment.

## Pre-Deployment Checklist

1. ✅ Set up Discord application and bot token
2. ✅ Get OpenAI API key
3. ✅ Configure environment variables
4. ✅ Test locally with `npm run dev`
5. ✅ Build project with `npm run build`
6. ✅ Test production build with `npm run start`
7. ✅ Ensure database is accessible
8. ✅ Update any hardcoded localhost references to 0.0.0.0

## Port Configuration
- Development: Port 5000
- Production: Use PORT environment variable or default to 5000
- Ensure server listens on 0.0.0.0 for external access

## Build Commands for Render
- Build Command: `npm install && npm run build`
- Start Command: `npm run start`
