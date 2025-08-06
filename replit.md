# SecureLink Remote Access Portal

## Overview

SecureLink is a comprehensive remote access portal designed to provide secure, silent access to devices through a web-based interface. The system consists of three main components: a React-based web portal for user interaction, a Node.js/Express backend server for authentication and device management, and lightweight Python agents that run on target devices to enable remote control capabilities.

The platform enables users to remotely access their devices through various interfaces including terminal access, file browsing, and session monitoring. The system emphasizes security through JWT-based authentication, encrypted communications, and device token validation.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript for type safety and developer experience
- **UI Library**: Shadcn/ui components built on Radix UI primitives for accessible, customizable interface elements
- **Styling**: Tailwind CSS with a dark theme design system using CSS custom properties
- **State Management**: TanStack Query for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Build Tool**: Vite for fast development and optimized production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript for type safety across the full stack
- **Authentication**: JWT (JSON Web Tokens) for stateless user sessions
- **Real-time Communication**: WebSocket server for bidirectional communication with devices and users
- **Session Management**: In-memory storage with interface for potential database integration
- **Security**: bcrypt for password hashing, HTTPS/WSS protocols

### Database Design
- **ORM**: Drizzle ORM for type-safe database operations
- **Database**: PostgreSQL configured through Neon serverless
- **Schema**: Comprehensive tables for users, devices, sessions, and access logs
- **Migrations**: Drizzle Kit for database schema management

### Key Data Models
- **Users**: Authentication credentials and profile information
- **Devices**: Registered remote devices with authentication tokens and status
- **Sessions**: Active remote access sessions with type tracking (terminal, file, screen)
- **Access Logs**: Audit trail of all user actions and device interactions

### Authentication & Authorization
- **User Authentication**: JWT-based session management with localStorage persistence
- **Device Authentication**: Unique auth tokens for each registered device
- **WebSocket Security**: Token-based authentication for real-time connections
- **Authorization**: User-device association for access control

### Communication Protocol
- **HTTP/HTTPS**: RESTful API for user authentication and device management
- **WebSocket/WSS**: Real-time bidirectional communication for remote sessions
- **Message Types**: Structured message protocol for terminal commands, file operations, and status updates

### Development & Deployment
- **Development Server**: Vite development server with HMR and Express API integration
- **Build Process**: Vite for frontend bundling, esbuild for backend compilation
- **Environment**: Replit-optimized with custom error handling and development tools

## External Dependencies

### Core Framework Dependencies
- **@neondatabase/serverless**: Serverless PostgreSQL database connection
- **drizzle-orm**: Type-safe ORM for database operations
- **drizzle-kit**: Database migration and schema management tools
- **express**: Web application framework for Node.js
- **ws**: WebSocket library for real-time communication

### Authentication & Security
- **bcrypt**: Password hashing and verification
- **jsonwebtoken**: JWT token generation and validation
- **connect-pg-simple**: PostgreSQL session store (configured but not actively used)

### Frontend Libraries
- **@tanstack/react-query**: Server state management and caching
- **react-hook-form**: Form handling with validation
- **@hookform/resolvers**: Form validation resolvers
- **zod**: Runtime type validation and schema definition
- **wouter**: Lightweight React routing

### UI Component Libraries
- **@radix-ui/***: Comprehensive set of accessible UI primitives
- **lucide-react**: Icon library for consistent iconography
- **tailwindcss**: Utility-first CSS framework
- **class-variance-authority**: Type-safe variant management for components

### Development Tools
- **typescript**: Static type checking
- **vite**: Build tool and development server
- **@replit/vite-plugin-runtime-error-modal**: Development error handling
- **tsx**: TypeScript execution for development scripts

### Agent Dependencies (Python)
- **websockets**: WebSocket client for device communication
- **asyncio**: Asynchronous I/O for concurrent operations
- **pathlib**: File system path manipulation