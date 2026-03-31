# GORA HRMS AI Backend

Python FastAPI backend for AI-powered features in GORA HRMS.

## Setup

1. **Create virtual environment:**
```bash
python -m venv venv
```

2. **Activate virtual environment:**
```bash
# Windows
venv\Scripts\activate

# Linux/Mac
source venv/bin/activate
```

3. **Install dependencies:**
```bash
pip install -r requirements.txt
```

4. **Configure environment:**
```bash
cp .env.example .env
# Edit .env with your credentials
```

5. **Run the server:**
```bash
python main.py
# Or with uvicorn
uvicorn main:app --reload --port 8000
```

## API Endpoints

### Health Check
- `GET /` - Root endpoint
- `GET /health` - Health check

### AI Features (Future Implementation)

#### Attendance Analysis
- `POST /api/ai/analyze-attendance`
- Analyzes attendance patterns and detects anomalies

#### Leave Prediction
- `POST /api/ai/predict-leaves`
- Predicts leave patterns and trends

#### HR Recommendations
- `POST /api/ai/recommend-actions`
- Suggests HR actions based on data analysis

#### AI Chat Assistant
- `POST /api/ai/chat`
- Natural language interface for HR queries

## Future Enhancements

### Phase 1: Data Analysis
- Implement attendance pattern analysis
- Leave trend prediction
- Employee performance insights

### Phase 2: ML Models
- Attrition prediction
- Optimal shift scheduling
- Workload balancing

### Phase 3: NLP Integration
- AI chat assistant with LLM
- Document processing
- Sentiment analysis from feedback

### Phase 4: Advanced Features
- Vector search with pgvector
- Semantic search across HR documents
- Intelligent recommendations

## Technology Stack

- **Framework:** FastAPI
- **Database:** PostgreSQL (Supabase)
- **Future AI:** OpenAI, LangChain, pgvector
- **ML:** scikit-learn, pandas, numpy

## Development

```bash
# Run with auto-reload
uvicorn main:app --reload

# Run tests (when implemented)
pytest

# Format code
black .

# Lint
flake8
```

## Deployment

### Docker (Future)
```dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

### Vercel/Railway
- Configure as Python app
- Set environment variables
- Deploy

## Integration with Next.js

The Next.js frontend can call these AI endpoints:

```typescript
// Example usage
const response = await fetch('http://localhost:8000/api/ai/analyze-attendance', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    query: 'Analyze last month attendance',
    context: { month: 3, year: 2026 }
  })
})
```

## License

Proprietary - GORA Computers
