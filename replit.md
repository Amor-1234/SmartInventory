# HappyShop - Family Inventory Management App

## Overview

HappyShop is a full-stack household inventory management and shopping list application designed for multi-device accessibility. The app allows family members to collaboratively track inventory, manage shopping lists, and maintain historical data across different user roles. Built with a modern TypeScript stack, it features a React frontend with shadcn/ui components and an Express.js backend using Drizzle ORM with PostgreSQL.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side navigation
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state
- **Forms**: React Hook Form with Zod validation
- **Icons**: Lucide React with emoji-based user avatars

### Backend Architecture  
- **Framework**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM for type-safe database operations
- **Authentication**: Replit Auth with OpenID Connect
- **Session Management**: Express session with PostgreSQL store
- **API Design**: RESTful endpoints with consistent error handling
- **Build Tool**: ESBuild for production bundling

### Development Environment
- **Build Tool**: Vite for development server and frontend builds
- **Package Manager**: npm with ES modules
- **TypeScript**: Strict configuration with path mapping
- **Development**: Hot module replacement and runtime error overlay

## Key Components

### Authentication System
- **Provider**: Replit Auth using OpenID Connect
- **Session Storage**: PostgreSQL-backed sessions with 7-day TTL
- **User Management**: Profile completion flow with role and icon selection
- **Authorization**: Role-based access control (Primary, Review, Kids, Principal)

### Database Schema
- **Users Table**: Extended with role, icon selection, and profile data
- **Inventory Items**: Core items with image support and creator tracking
- **Inventory History**: Weekly tracking with manual adjustment capabilities
- **Shopping Lists**: Auto-generated from inventory data with completion tracking
- **Notes System**: Item-specific notes with user attribution
- **Reviews**: Multi-user item review and discussion system

### Core Features
- **Multi-Column Inventory View**: Past inventory, shopping history, current stock
- **Auto Shopping List Generation**: Calculated from inventory patterns
- **Image Support**: Default grocery images with modal viewing
- **Notes and Reviews**: Collaborative item discussions
- **Export/Share**: Shopping list export and native sharing
- **Mobile Responsive**: Optimized for phones, tablets, and desktops

## Data Flow

### Inventory Management
1. Users update current inventory levels in the dashboard
2. System calculates shopping needs based on historical patterns
3. Auto-generated shopping lists update in real-time
4. Historical data tracks patterns for future predictions

### Shopping Workflow
1. Shopping list auto-populates from inventory calculations
2. Users can add notes and mark items as completed
3. Uncompleted items carry over to next shopping session
4. Discussion notes generate for family coordination

### User Collaboration
1. Multiple family roles with different permissions
2. User icons track who created/modified items
3. Notes and reviews enable family communication
4. Real-time updates across all connected devices

## External Dependencies

### Core Framework Dependencies
- **React Ecosystem**: React 18, React Router (Wouter), TanStack Query
- **UI Components**: Radix UI primitives, shadcn/ui component library
- **Styling**: Tailwind CSS, class-variance-authority for component variants
- **Forms**: React Hook Form, Hookform resolvers, Zod validation

### Backend Dependencies
- **Database**: Neon PostgreSQL serverless with connection pooling
- **ORM**: Drizzle ORM with Drizzle Kit for migrations
- **Authentication**: OpenID Client, Passport.js strategies
- **Session**: Express session with PostgreSQL storage (connect-pg-simple)

### Development Tools
- **Build**: Vite, ESBuild, TypeScript compiler
- **Replit Integration**: Vite plugins for development environment
- **Utilities**: date-fns, memoizee, nanoid for various helper functions

## Deployment Strategy

### Production Build
- **Frontend**: Vite builds optimized React bundle to `dist/public`
- **Backend**: ESBuild compiles Express server to `dist/index.js`
- **Assets**: Static files served from build output directory
- **Environment**: Production environment variables for database and auth

### Development Workflow
- **Database**: Drizzle Kit handles schema migrations and pushes
- **Hot Reload**: Vite dev server with Express API proxy
- **Environment**: Development-specific logging and error handling
- **Scripts**: npm scripts for development, build, and database operations

### Hosting Requirements
- **Database**: PostgreSQL with connection string via DATABASE_URL
- **Authentication**: Replit Auth configuration with OIDC endpoints
- **Sessions**: Secure session storage with generated secrets
- **Static Files**: Efficient serving of built assets and images