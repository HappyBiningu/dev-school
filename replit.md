# School ERP

A full-stack School ERP (Enterprise Resource Planning) system for managing students, academics, attendance, and more.

## Architecture

- **Frontend**: Next.js 15 (with Turbopack) + Tailwind CSS + shadcn/ui components, running on port 5000
- **Backend**: NestJS 11, running on port 3000

## Project Structure

```
├── frontend/        # Next.js application
│   ├── src/
│   │   ├── app/         # Next.js App Router pages
│   │   │   ├── (auth)/      # Auth layout group
│   │   │   └── (dashboard)/ # Dashboard layout group
│   │   ├── components/  # Shared UI components
│   │   ├── config/      # App configuration
│   │   ├── hooks/       # Custom React hooks
│   │   ├── icons/       # Icon components
│   │   ├── lib/         # Utility functions
│   │   └── providers/   # React context providers
│   └── next.config.ts   # Next.js configuration
├── backend/         # NestJS application
│   └── src/
│       ├── app.module.ts
│       ├── app.controller.ts
│       ├── app.service.ts
│       └── main.ts      # Binds to 0.0.0.0:3000
└── doc/             # Feature documentation
```

## Workflows

- **Start application**: `cd frontend && npm run dev -- --port 5000 --hostname 0.0.0.0` (webview, port 5000)
- **Backend API**: `cd backend && npm run start:dev` (console, port 3000)

## Key Configuration

- Frontend runs on `0.0.0.0:5000` for Replit proxy compatibility
- Backend runs on `0.0.0.0:3000`
- Deployment: autoscale target, builds frontend with `npm run build`, runs both services
