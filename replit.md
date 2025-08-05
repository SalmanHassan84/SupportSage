# RAG Support Assistant

## Overview

This project is a document-powered AI support system that implements Retrieval-Augmented Generation (RAG) to answer questions based on uploaded documents. The system processes documents (PDF, CSV, TXT), creates vector embeddings, and uses OpenAI's GPT models to provide intelligent responses with source citations.

The application features a modern web interface built with React and shadcn/ui components, allowing users to upload documents, monitor processing status, ask questions, and view AI-generated answers with relevant source references.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with CSS variables for theming
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **File Uploads**: react-dropzone for drag-and-drop file upload interface

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM with PostgreSQL dialect
- **File Processing**: Custom document processors for PDF, CSV, and TXT files
- **Vector Operations**: Custom vector service for embedding generation and similarity search
- **Session Storage**: In-memory storage with interface for future database integration

### Data Storage Solutions
- **Primary Database**: PostgreSQL configured through Drizzle ORM
- **Vector Storage**: Embeddings stored as arrays in PostgreSQL
- **File Storage**: Local filesystem for uploaded documents
- **Session Storage**: Currently in-memory (MemStorage) with interface for database persistence

### Database Schema
- **Users**: Authentication and user management
- **Documents**: File metadata, processing status, and extracted content
- **Document Chunks**: Text segments with vector embeddings for similarity search
- **Queries**: User questions, AI responses, confidence scores, and source citations

### AI and ML Integration
- **Embedding Model**: OpenAI's text-embedding-3-small for vector generation
- **Language Model**: OpenAI GPT for response generation
- **Vector Search**: Cosine similarity for finding relevant document chunks
- **RAG Pipeline**: Custom implementation combining retrieval and generation

### Authentication and Authorization
- Currently uses a basic user system with username/password
- Session management through storage interface
- No complex role-based permissions implemented

## External Dependencies

### Core Services
- **OpenAI API**: For text embeddings and GPT-based response generation
- **Neon Database**: PostgreSQL hosting service for data persistence
- **Replit**: Development platform integration with custom plugins

### Development Tools
- **Vite**: Frontend build tool and development server
- **Drizzle Kit**: Database schema management and migrations
- **ESBuild**: Backend bundling for production builds

### UI and Styling
- **Radix UI**: Accessible component primitives
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library
- **React Hook Form**: Form validation and management

### File Processing
- **Multer**: Express middleware for handling file uploads
- **Custom Parsers**: Built-in text extraction for supported file types

### Monitoring and Development
- **TanStack Query**: Data fetching and caching
- **React Query DevTools**: Development debugging
- **Replit Runtime Error Modal**: Error handling in development