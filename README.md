# 🚀 Hackathon Builder

A comprehensive AI-powered tool that analyzes hackathon requirements and generates winning project ideas tailored to specific competitions and sponsor prizes.

## 🎯 Features

### 📋 Hackathon Analysis
- **URL Processing**: Extract requirements from hackathon websites
- **Document Analysis**: Parse PDF/text documentation for competition details
- **Sponsor Prize Detection**: Identify sponsor categories and prize criteria
- **Theme Extraction**: Understand hackathon themes and focus areas

### 💡 Idea Generation
- **AI-Powered Suggestions**: Generate creative project ideas using advanced AI
- **Requirement Matching**: Ensure ideas align with hackathon criteria
- **Prize Optimization**: Maximize potential for winning sponsor prizes
- **Difficulty Assessment**: Evaluate project feasibility within time constraints

### ✅ Idea Validation
- **Criteria Scoring**: Rate ideas against judging criteria
- **Feasibility Analysis**: Assess technical complexity and time requirements
- **Market Validation**: Evaluate real-world impact and innovation
- **Improvement Suggestions**: Provide actionable feedback for idea refinement

## 🛠️ Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/hackathon-builder.git
cd hackathon-builder

# Install dependencies
npm install

# Set up environment variables
cp .env.example .env
# Edit .env with your API keys
```

## 🚦 Quick Start

```bash
# Start development server
npm run dev

# Open your browser to http://localhost:3000
```

## 📝 Usage

### Basic Usage

1. **Input Hackathon Details**
   ```
   - Paste hackathon URL or upload documentation
   - System automatically extracts requirements and prizes
   ```

2. **Generate Ideas**
   ```
   - Click "Generate Ideas" to get AI-powered suggestions
   - Filter by difficulty, category, or sponsor prizes
   ```

3. **Validate & Refine**
   ```
   - Review idea scores and validation feedback
   - Iterate on ideas based on suggestions
   ```

### API Usage

```javascript
// Generate ideas for a hackathon
const ideas = await generateIdeas({
  hackathonUrl: 'https://example-hackathon.com',
  preferences: {
    difficulty: 'medium',
    categories: ['AI', 'Web3'],
    teamSize: 4
  }
});

// Validate an idea
const validation = await validateIdea({
  idea: 'AI-powered sustainability tracker',
  hackathonCriteria: criteria
});
```

## 🏗️ Architecture

```
hackathon-builder/
├── src/
│   ├── components/          # React components
│   │   ├── IdeaGenerator/
│   │   ├── ValidationEngine/
│   │   └── HackathonAnalyzer/
│   ├── services/           # Business logic
│   │   ├── analyzer.ts     # Hackathon parsing
│   │   ├── generator.ts    # Idea generation
│   │   └── validator.ts    # Idea validation
│   ├── utils/              # Utility functions
│   ├── types/              # TypeScript definitions
│   └── hooks/              # Custom React hooks
├── tests/                  # Test files
├── docs/                   # Documentation
└── public/                 # Static assets
```

## 🧪 Testing

```bash
# Run all tests
npm test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage

# Run specific test file
npm test -- IdeaGenerator.test.ts
```

## 🔧 Development

### Prerequisites
- Node.js 18+
- npm or yarn
- API keys for AI services (OpenAI, Anthropic, etc.)

### Environment Variables

```bash
# .env
OPENAI_API_KEY=your_openai_key
ANTHROPIC_API_KEY=your_anthropic_key
DATABASE_URL=your_database_url
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Code Quality

```bash
# Lint code
npm run lint

# Fix linting issues
npm run lint:fix

# Type checking
npm run typecheck

# Format code
npm run format
```

## 📊 Performance

- **Analysis Speed**: < 30 seconds for most hackathon URLs
- **Idea Generation**: 5-10 creative ideas in < 60 seconds
- **Validation**: Comprehensive scoring in < 15 seconds

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow TypeScript best practices
- Write tests for new features
- Update documentation for API changes
- Use conventional commits for commit messages

## 📄 API Documentation

### Core Endpoints

#### `POST /api/analyze`
Analyze hackathon requirements from URL or document.

```typescript
interface AnalyzeRequest {
  url?: string;
  document?: File;
  customRequirements?: string[];
}

interface AnalyzeResponse {
  requirements: Requirement[];
  sponsors: Sponsor[];
  themes: string[];
  deadlines: Date[];
}
```

#### `POST /api/generate`
Generate project ideas based on analysis.

```typescript
interface GenerateRequest {
  hackathonId: string;
  preferences: {
    difficulty: 'easy' | 'medium' | 'hard';
    categories: string[];
    teamSize: number;
  };
}

interface GenerateResponse {
  ideas: ProjectIdea[];
  reasoning: string;
}
```

#### `POST /api/validate`
Validate a project idea against criteria.

```typescript
interface ValidateRequest {
  idea: ProjectIdea;
  criteria: ValidationCriteria;
}

interface ValidateResponse {
  score: number;
  feedback: Feedback[];
  suggestions: string[];
}
```

## 🔒 Security

- All API keys are encrypted at rest
- Input validation on all endpoints
- Rate limiting on generation endpoints
- CORS protection enabled

## 📈 Roadmap

- [ ] **V2.0**: Real-time collaboration on ideas
- [ ] **V2.1**: Integration with GitHub for project setup
- [ ] **V2.2**: Team matching based on skills and ideas
- [ ] **V3.0**: Mobile app for on-the-go idea generation


**Made with ❤️ for the hackathon community**