# Overview

This is a full-stack web application called "Will it Rain on My Parade?" - a NASA Space Apps Challenge 2024 project that predicts the likelihood of rain for a user-specified week at a given location. The application combines machine learning techniques with real-time weather data to provide intelligent rain forecasting with interactive visualizations.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Library**: Radix UI components with shadcn/ui design system
- **Styling**: Tailwind CSS with CSS variables for theming (dark theme by default)
- **State Management**: React Query (TanStack Query) for server state management
- **Routing**: Wouter for client-side routing
- **Visualization**: Plotly.js for interactive weather charts and data visualization
- **Design Pattern**: Component-based architecture with reusable UI components

## Backend Architecture
- **Framework**: Express.js with TypeScript running on Node.js
- **API Pattern**: RESTful API endpoints with JSON responses
- **Data Validation**: Zod schemas for type-safe request/response validation
- **Storage**: In-memory storage implementation (MemStorage) with interface for future database integration
- **Machine Learning**: Client-side ML prediction utilities for ARIMA-like forecasting
- **Development**: Hot module replacement with Vite integration for seamless development

## Database Design
- **ORM**: Drizzle ORM configured for PostgreSQL
- **Tables**: 
  - `users` - User authentication and profiles
  - `weather_predictions` - Cached prediction results with location data, forecasts, and ML model contributions
- **Schema**: Type-safe database schemas with Zod validation integration

## Authentication & Authorization
- Basic user management system with username/password authentication
- Session-based authentication preparation (connect-pg-simple for PostgreSQL sessions)
- No authentication currently implemented in routes (preparation for future implementation)

## External Service Integrations
- **Weather API**: OpenWeatherMap API for real-time weather data and forecasting
- **Geocoding**: OpenWeatherMap Geocoding API for location coordinate resolution
- **Fallback Strategy**: Multiple API endpoints with graceful degradation from One Call API to standard weather/forecast APIs

# External Dependencies

## Third-Party APIs
- **OpenWeatherMap**: Primary weather data provider requiring API key
  - One Call API 3.0 for comprehensive weather data
  - Current Weather API as fallback
  - 5-day Forecast API for extended predictions
  - Geocoding API for location services

## Database Services
- **Neon Database**: Serverless PostgreSQL database (@neondatabase/serverless)
- **Connection**: Environment variable `DATABASE_URL` required for database connectivity

## Development & Deployment
- **Replit Integration**: Custom Vite plugins for development environment
  - Runtime error modal overlay
  - Development banner
  - Cartographer for code mapping
- **Build Tools**: ESBuild for server bundling, Vite for client bundling

## UI & Visualization Libraries
- **Component Library**: Extensive Radix UI primitive components
- **Charts**: Plotly.js for interactive data visualization
- **Styling**: Tailwind CSS with PostCSS processing
- **Icons**: Lucide React for consistent iconography

## Utility Libraries
- **Date Handling**: date-fns for date manipulation and formatting
- **Form Management**: React Hook Form with Hookform Resolvers
- **Validation**: Zod for runtime type checking and validation
- **State Management**: TanStack React Query for server state caching
- **Styling Utilities**: clsx and class-variance-authority for conditional styling