# Idea-Generator-App

# AI Content Generator

A web-based AI content generator that creates various creative outputs based on user-provided topics or industries.

## Features

- Generate content across multiple categories:
  - Blog post ideas
  - Startup names
  - Social media posts
  - YouTube video titles
  - Slogans & taglines

- Advanced functionality:
  - Content favorites
  - Multi-format output
  - Topic suggestions
  - Light/dark mode

- Technical features:
  - OpenAI API integration
  - PostgreSQL database for persistent storage
  - Demo mode fallback when API quota is exceeded

## Architecture

### Database Schema

The application uses a PostgreSQL database with the following structure:

```
users
├── id (PK)
├── username
└── password

content_items
├── id (PK)
├── userId (FK -> users.id) [nullable]
├── type
├── topic
├── content
├── description
├── tags
├── platform
├── isFavorite
└── createdAt
```

### API Endpoints

- `POST /api/generate` - Generate content based on topic and type
- `POST /api/content/:id/favorite` - Toggle favorite status for content item
- `GET /api/favorites` - Get all favorite content items

## Demo Mode

When the OpenAI API quota is exceeded or the API key is unavailable, the application automatically falls back to demo mode, which provides template-based content generation while maintaining the same user experience.

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL database
- OpenAI API key

### Installation

1. Clone the repository
2. Install dependencies with `npm install`
3. Configure environment variables (see below)
4. Run the application with `npm run dev`

### Environment Variables

- `DATABASE_URL` - PostgreSQL connection string
- `OPENAI_API_KEY` - Your OpenAI API key

## Future Improvements

- User authentication and profiles
- Content history by user
- Multiple saved topics
- Enhanced favorites organization
- Export to various formats (PDF, social media)
