# 📁 BoliAI Project Structure

## Directory Overview

```
BoliAI/
├── frontend/                 # React web application
│   ├── public/              # Static assets
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── services/       # API calls and external services
│   │   ├── utils/          # Helper functions
│   │   ├── hooks/          # Custom React hooks
│   │   ├── context/        # React Context for state management
│   │   ├── assets/         # Images, fonts, icons
│   │   └── styles/         # Global styles and Tailwind config
│   ├── package.json
│   └── README.md
│
├── backend/                 # Node.js/Express API server
│   ├── src/
│   │   ├── routes/         # API route definitions
│   │   ├── controllers/    # Business logic
│   │   ├── models/         # Database models
│   │   ├── middleware/     # Auth, validation, etc.
│   │   ├── services/       # External API integrations
│   │   │   ├── openai.js   # GPT-4 integration
│   │   │   ├── google-translate.js
│   │   │   └── google-tts.js
│   │   ├── utils/          # Helper functions
│   │   └── config/         # Configuration files
│   ├── package.json
│   └── README.md
│
├── docs/                    # Documentation
│   ├── PROJECT_STRUCTURE.md
│   ├── INTER_STATE_USE_CASES.md
│   ├── API_DOCUMENTATION.md
│   ├── DEPLOYMENT_GUIDE.md
│   └── CONTRIBUTING.md
│
├── assets/                  # Shared assets
│   ├── logos/
│   ├── screenshots/
│   └── pitch-deck/
│
├── .gitignore
├── README.md
└── LICENSE
```

---

## 🎨 Frontend Structure (Detailed)

```
frontend/
├── public/
│   ├── index.html
│   ├── favicon.ico
│   ├── manifest.json
│   └── robots.txt
│
├── src/
│   ├── components/
│   │   ├── common/
│   │   │   ├── Header.jsx
│   │   │   ├── Footer.jsx
│   │   │   ├── Button.jsx
│   │   │   ├── Input.jsx
│   │   │   ├── Modal.jsx
│   │   │   └── Loading.jsx
│   │   │
│   │   ├── learning/
│   │   │   ├── ModeSelector.jsx        # Culture/Job/Fun/Casual/Travel
│   │   │   ├── SearchBar.jsx           # Multi-language search
│   │   │   ├── TranslationCard.jsx     # Display translations
│   │   │   ├── AudioPlayer.jsx         # Pronunciation playback
│   │   │   ├── Flashcard.jsx           # Spaced repetition cards
│   │   │   └── ProgressTracker.jsx     # User progress visualization
│   │   │
│   │   ├── auth/
│   │   │   ├── LoginForm.jsx
│   │   │   ├── SignupForm.jsx
│   │   │   └── ProfileSettings.jsx
│   │   │
│   │   └── dashboard/
│   │       ├── UserDashboard.jsx
│   │       ├── LearningStats.jsx
│   │       └── SavedPhrases.jsx
│   │
│   ├── pages/
│   │   ├── Home.jsx                    # Landing page
│   │   ├── Learn.jsx                   # Main learning interface
│   │   ├── Dashboard.jsx               # User dashboard
│   │   ├── Pricing.jsx                 # Subscription plans
│   │   ├── About.jsx                   # About BoliAI
│   │   └── NotFound.jsx                # 404 page
│   │
│   ├── services/
│   │   ├── api.js                      # Axios instance and config
│   │   ├── translationService.js       # Translation API calls
│   │   ├── authService.js              # Authentication
│   │   ├── userService.js              # User data management
│   │   └── audioService.js             # TTS and audio playback
│   │
│   ├── hooks/
│   │   ├── useTranslation.js           # Translation hook
│   │   ├── useAudio.js                 # Audio playback hook
│   │   ├── useAuth.js                  # Authentication hook
│   │   └── useLocalStorage.js          # Local storage management
│   │
│   ├── context/
│   │   ├── AuthContext.jsx             # User authentication state
│   │   ├── LanguageContext.jsx         # Selected languages
│   │   └── ThemeContext.jsx            # Dark/light mode
│   │
│   ├── utils/
│   │   ├── constants.js                # App constants
│   │   ├── helpers.js                  # Utility functions
│   │   └── validators.js               # Form validation
│   │
│   ├── assets/
│   │   ├── images/
│   │   ├── icons/
│   │   └── fonts/
│   │
│   ├── styles/
│   │   ├── globals.css                 # Global styles
│   │   └── tailwind.config.js          # Tailwind configuration
│   │
│   ├── App.jsx                         # Main app component
│   ├── index.js                        # Entry point
│   └── routes.js                       # Route definitions
│
├── .env.example                        # Environment variables template
├── package.json
├── tailwind.config.js
└── README.md
```

---

## 🔧 Backend Structure (Detailed)

```
backend/
├── src/
│   ├── routes/
│   │   ├── auth.routes.js              # /api/auth/*
│   │   ├── translation.routes.js       # /api/translate/*
│   │   ├── user.routes.js              # /api/users/*
│   │   ├── flashcard.routes.js         # /api/flashcards/*
│   │   └── audio.routes.js             # /api/audio/*
│   │
│   ├── controllers/
│   │   ├── authController.js           # Login, signup, logout
│   │   ├── translationController.js    # Translation logic
│   │   ├── userController.js           # User CRUD operations
│   │   ├── flashcardController.js      # Flashcard management
│   │   └── audioController.js          # TTS generation
│   │
│   ├── models/
│   │   ├── User.js                     # User schema
│   │   ├── Translation.js              # Translation history
│   │   ├── Flashcard.js                # Flashcard data
│   │   └── Progress.js                 # Learning progress
│   │
│   ├── middleware/
│   │   ├── auth.middleware.js          # JWT verification
│   │   ├── validation.middleware.js    # Request validation
│   │   ├── rateLimit.middleware.js     # API rate limiting
│   │   └── error.middleware.js         # Error handling
│   │
│   ├── services/
│   │   ├── openai.service.js           # GPT-4 API integration
│   │   │   ├── contextualTranslation() # Context-aware translation
│   │   │   ├── culturalNotes()         # Generate cultural context
│   │   │   └── conversationPractice()  # Chat-based learning
│   │   │
│   │   ├── google-translate.service.js # Google Translate API
│   │   │   ├── translateText()
│   │   │   ├── detectLanguage()
│   │   │   └── getSupportedLanguages()
│   │   │
│   │   ├── google-tts.service.js       # Text-to-Speech
│   │   │   ├── generateAudio()
│   │   │   └── getVoiceOptions()
│   │   │
│   │   ├── supabase.service.js         # Database operations
│   │   │   ├── createUser()
│   │   │   ├── saveTranslation()
│   │   │   └── getUserProgress()
│   │   │
│   │   └── cache.service.js            # Redis caching (future)
│   │
│   ├── utils/
│   │   ├── logger.js                   # Logging utility
│   │   ├── validators.js               # Input validation
│   │   └── helpers.js                  # Helper functions
│   │
│   ├── config/
│   │   ├── database.js                 # Supabase config
│   │   ├── openai.js                   # OpenAI config
│   │   ├── google.js                   # Google Cloud config
│   │   └── constants.js                # App constants
│   │
│   ├── app.js                          # Express app setup
│   └── server.js                       # Server entry point
│
├── .env.example
├── package.json
└── README.md
```

---

## 🗄️ Database Schema (Supabase/PostgreSQL)

```sql
-- Users table
CREATE TABLE users (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  name VARCHAR(255),
  native_language VARCHAR(50),
  learning_languages TEXT[], -- Array of languages
  subscription_tier VARCHAR(50) DEFAULT 'free',
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Translations table (history)
CREATE TABLE translations (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  source_text TEXT NOT NULL,
  source_language VARCHAR(50) NOT NULL,
  target_language VARCHAR(50) NOT NULL,
  translated_text TEXT NOT NULL,
  mode VARCHAR(50), -- culture, job, fun, casual, travel
  cultural_notes TEXT,
  audio_url TEXT,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Flashcards table
CREATE TABLE flashcards (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  front_text TEXT NOT NULL,
  back_text TEXT NOT NULL,
  language VARCHAR(50) NOT NULL,
  category VARCHAR(50),
  difficulty INT DEFAULT 1,
  next_review_date TIMESTAMP,
  review_count INT DEFAULT 0,
  created_at TIMESTAMP DEFAULT NOW()
);

-- User progress table
CREATE TABLE user_progress (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  language VARCHAR(50) NOT NULL,
  phrases_learned INT DEFAULT 0,
  daily_streak INT DEFAULT 0,
  total_study_time INT DEFAULT 0, -- in minutes
  last_study_date TIMESTAMP,
  created_at TIMESTAMP DEFAULT NOW(),
  updated_at TIMESTAMP DEFAULT NOW()
);

-- Saved phrases table
CREATE TABLE saved_phrases (
  id UUID PRIMARY KEY DEFAULT uuid_generate_v4(),
  user_id UUID REFERENCES users(id),
  phrase TEXT NOT NULL,
  translation TEXT NOT NULL,
  language VARCHAR(50) NOT NULL,
  category VARCHAR(50),
  notes TEXT,
  created_at TIMESTAMP DEFAULT NOW()
);
```

---

## 🔑 Environment Variables

### Frontend (.env)
```
REACT_APP_API_URL=http://localhost:5000/api
REACT_APP_SUPABASE_URL=your_supabase_url
REACT_APP_SUPABASE_ANON_KEY=your_supabase_anon_key
```

### Backend (.env)
```
PORT=5000
NODE_ENV=development

# Supabase
SUPABASE_URL=your_supabase_url
SUPABASE_SERVICE_KEY=your_supabase_service_key

# OpenAI
OPENAI_API_KEY=your_openai_api_key

# Google Cloud
GOOGLE_CLOUD_PROJECT_ID=your_project_id
GOOGLE_CLOUD_API_KEY=your_google_api_key

# JWT
JWT_SECRET=your_jwt_secret
JWT_EXPIRES_IN=7d

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

---

## 📦 Key Dependencies

### Frontend
```json
{
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.20.0",
    "axios": "^1.6.0",
    "@supabase/supabase-js": "^2.38.0",
    "tailwindcss": "^3.3.0",
    "lucide-react": "^0.300.0"
  }
}
```

### Backend
```json
{
  "dependencies": {
    "express": "^4.18.2",
    "@supabase/supabase-js": "^2.38.0",
    "openai": "^4.20.0",
    "@google-cloud/translate": "^8.0.0",
    "@google-cloud/text-to-speech": "^5.0.0",
    "bcryptjs": "^2.4.3",
    "jsonwebtoken": "^9.0.2",
    "express-rate-limit": "^7.1.0",
    "cors": "^2.8.5",
    "dotenv": "^16.3.1"
  }
}
```

---

## 🚀 Next Steps

1. **Initialize Git repository**
2. **Set up frontend with Create React App**
3. **Set up backend with Express**
4. **Configure Supabase database**
5. **Integrate OpenAI API**
6. **Build core translation feature**
7. **Deploy to Vercel (frontend) and Supabase (backend)**

---

**Ready to build! 🎉**
