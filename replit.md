# BizLaunch Toolkit - Empowering Young Women Entrepreneurs

## Overview

BizLaunch Toolkit is a full-stack web application designed to help teen girls launch their own businesses using AI-powered tools, mentorship matching, and practical resources. The platform combines business ideation, planning tools, content generation, and inspirational role model matching to create a comprehensive entrepreneurship toolkit.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query for server state management
- **UI Framework**: Shadcn/UI components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom design system and CSS variables
- **Form Handling**: React Hook Form with Zod validation

**Rationale**: This modern React stack provides excellent developer experience, performance, and maintainability. Shadcn/UI offers consistent, accessible components while Tailwind enables rapid UI development.

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript for type safety across the stack
- **API Design**: RESTful endpoints with JSON responses
- **Session Management**: Express sessions with in-memory storage (development)
- **File Structure**: Modular separation of routes, storage, and business logic

**Rationale**: Express provides a mature, flexible foundation for the API layer. TypeScript ensures type safety between frontend and backend through shared schemas.

### Data Storage Solutions
- **Database**: PostgreSQL with Drizzle ORM
- **Connection**: Neon Database serverless PostgreSQL
- **Schema Management**: Drizzle Kit for migrations and schema management
- **Development Storage**: In-memory storage implementation for rapid prototyping
- **Production Ready**: Database abstraction allows easy switching between storage implementations

**Rationale**: PostgreSQL provides robust relational data storage. Drizzle ORM offers type-safe database operations with excellent TypeScript integration. The storage abstraction pattern allows for flexible deployment options.

## Key Components

### Business Quiz System
- Interactive multi-step questionnaire to assess interests and preferences
- Weighted scoring algorithm to recommend business ideas
- Session-based progress tracking
- Results storage for future reference

### Checklist Generator
- Business-type specific startup checklists
- Progress tracking with completion status
- Persistent storage of user progress
- Visual progress indicators

### AI Content Generation
- **Business Pitch Generator**: Creates compelling elevator pitches using Google Gemini AI
- **Social Media Caption Generator**: Platform-specific content for Instagram, TikTok, etc.
- **Website Template Generator**: Basic HTML template generation for business websites
- Input validation and error handling for AI interactions

### STEM Mentor Matching
- Interest-based questionnaire system
- Database of successful women in STEM with biographical information
- Matching algorithm based on field alignment
- Inspirational quotes and achievements display

### UI/UX Components
- Responsive design with mobile-first approach
- Gradient-based color scheme (purple/pink theme)
- Smooth scrolling navigation between sections
- Toast notifications for user feedback
- Loading states and error handling

## Data Flow

1. **User Interaction**: Users interact with React components in the browser
2. **API Requests**: TanStack Query manages API calls to Express server
3. **Data Processing**: Server processes requests, validates data with Zod schemas
4. **AI Integration**: Gemini AI generates content based on user inputs
5. **Data Persistence**: Information stored via Drizzle ORM to PostgreSQL
6. **Response Handling**: JSON responses sent back to client
7. **UI Updates**: React components re-render with new data

## External Dependencies

### AI Services
- **Google Gemini AI**: Content generation for business pitches and social media captions
- **API Key Management**: Environment variable configuration for secure API access

### Database Services
- **Neon Database**: Serverless PostgreSQL hosting
- **Connection Management**: Environment-based DATABASE_URL configuration

### UI Libraries
- **Radix UI**: Accessibility-focused primitive components
- **Lucide React**: Icon library for consistent iconography
- **Class Variance Authority**: Component variant management
- **React Day Picker**: Calendar functionality

### Development Tools
- **ESBuild**: Fast JavaScript bundling for production
- **PostCSS**: CSS processing with Tailwind integration
- **Replit Integration**: Development environment optimizations

## Deployment Strategy

### Development Environment
- **Local Development**: Vite dev server with hot module replacement
- **Database**: Neon Database with development credentials
- **Environment Variables**: Local .env file for API keys and database URLs

### Production Build
- **Frontend**: Vite production build with optimized assets
- **Backend**: ESBuild compilation to single JavaScript bundle
- **Static Assets**: Served through Express static middleware
- **Database Migrations**: Drizzle Kit push for schema updates

### Environment Configuration
- **NODE_ENV**: Environment-specific behavior
- **DATABASE_URL**: PostgreSQL connection string
- **GEMINI_API_KEY**: Google AI API authentication
- **Port Configuration**: Flexible port assignment for different environments

### Scalability Considerations
- Session storage can be upgraded to Redis for multi-instance deployments
- Database connection pooling configured through Neon
- AI API rate limiting and error handling implemented
- Static asset caching through CDN deployment ready

The architecture prioritizes rapid development and deployment while maintaining production readiness through proper separation of concerns, type safety, and scalable patterns.