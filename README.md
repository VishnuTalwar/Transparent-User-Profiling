# 📰 Intelligent News Feed Application

A personalized news application that uses AI-powered content recommendation and transparent user profiling to deliver relevant news articles tailored to individual preferences.

## 🌟 Features

### Core Functionality
- **Personalized News Feed**: AI-driven article recommendations based on user behavior and preferences
- **Multi-Category Support**: Business, Entertainment, Health, Science, Sports, Technology, and General news
- **Advanced Search**: Keyword-based article filtering and discovery
- **User Authentication**: Secure registration and login system with JWT tokens
- **Article Interaction**: Save, like, and track reading activity
- **Real-time Updates**: Scheduled news fetching with background updates

### AI & Machine Learning
- **Transparent User Profiling**: Clear visibility into how recommendations are generated
- **Interest Profile Building**: Dynamic learning from user interactions (reads, likes, saves)
- **TF-IDF Content Analysis**: Advanced text analysis for better content matching
- **Activity-Based Recommendations**: Personalization based on reading patterns
- **Keyword Extraction**: NLP-powered content understanding using NLTK

### User Experience
- **Responsive Design**: Mobile-friendly interface with modern UI components
- **Preference Management**: Granular control over content categories and keywords
- **Data Transparency**: Optional data sharing with clear consent mechanisms
- **Saved Articles**: Personal article library with easy management
- **Location-Based Content**: Geographic preference settings

## 🏗️ Architecture

### Frontend
- **Framework**: Dash (Python web framework)
- **Styling**: Bootstrap components with custom CSS
- **Components**: Modular UI components for reusability
- **State Management**: Session-based authentication storage

### Backend
- **API**: FastAPI with automatic documentation
- **Authentication**: JWT-based secure authentication
- **Database**: MongoDB for user data and preferences
- **Scheduling**: APScheduler for automated news fetching
- **AI Engine**: Custom recommendation system with scikit-learn

### External Services
- **News API**: Real-time news data from newsapi.org
- **MongoDB**: Document-based storage for flexibility

## 📂 Project Structure

```
news-app/
├── frontend/
│   ├── app.py              # Main Dash application
│   ├── components.py       # UI components (login, news cards, layouts)
│   ├── callbacks.py        # Interactive callbacks and event handlers
│   └── api_client.py       # Frontend API communication layer
├── backend/
│   ├── main.py             # FastAPI server with all endpoints
│   └── ai_model.py         # ML recommendation engine
├── database/
│   └── mongo_handler.py    # Database utilities
├── news/
│   └── news_fetcher.py     # News API integration with caching
├── assets/
│   ├── custom.css          # Custom styling
│   ├── favicon.ico         # Application icon
│   └── cache/              # News data caching
└── requirements.txt        # Python dependencies
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- MongoDB (local or cloud instance)
- News API key from [newsapi.org](https://newsapi.org/)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd news-app
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Environment Setup**
   Create a `.env` file in the root directory:
   ```env
   NEWS_API_KEY=your_news_api_key_here
   MONGO_URI=mongodb://localhost:27017/
   SECRET_KEY=your_secret_key_here
   API_BASE_URL=http://localhost:8000/api
   ```

4. **Start MongoDB**
   ```bash
   # For local MongoDB
   mongod
   
   # Or use MongoDB Atlas (cloud)
   # Update MONGO_URI in .env with your connection string
   ```

5. **Run the Backend**
   ```bash
   cd backend
   python main.py
   # Backend runs on http://localhost:8000
   ```

6. **Run the Frontend**
   ```bash
   cd frontend
   python app.py
   # Frontend runs on http://localhost:8050
   ```

7. **Access the Application**
   Open your browser and navigate to: `http://localhost:8050`

## 🔧 Configuration

### Environment Variables
- `NEWS_API_KEY`: Your News API key (required)
- `MONGO_URI`: MongoDB connection string
- `SECRET_KEY`: JWT secret key for authentication
- `API_BASE_URL`: Backend API base URL

### News API Setup
1. Visit [newsapi.org](https://newsapi.org/)
2. Register for a free API key
3. Add the key to your `.env` file

### MongoDB Configuration
- **Local**: Install MongoDB and run `mongod`
- **Cloud**: Use MongoDB Atlas for cloud hosting
- **Docker**: Run MongoDB in a Docker container

## 🤖 AI & Recommendation System

### How It Works
1. **User Profiling**: Tracks interests based on article interactions
2. **Content Analysis**: Extracts keywords and analyzes article content
3. **Similarity Matching**: Uses TF-IDF for content similarity
4. **Preference Learning**: Adapts to user behavior over time

### Transparency Features
- **Clear Explanations**: Each recommendation shows why it was suggested
- **Interest Visibility**: Users can see their extracted interests
- **Data Control**: Granular privacy settings
- **Opt-in Features**: Experimental features require explicit consent

## 🔗 API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login

### News
- `POST /api/news/fetch` - Fetch filtered news
- `GET /api/news/personalized` - Get personalized recommendations
- `GET /api/news/explore` - Browse trending articles
- `GET /api/news/categories` - Available news categories

### User Management
- `GET /api/user/preferences` - Get user preferences
- `PUT /api/user/preferences` - Update preferences
- `POST /api/user/save-article/{id}` - Save article
- `POST /api/user/like-article/{id}` - Like article
- `GET /api/user/saved-articles` - Get saved articles

## 🎨 Customization

### Styling
- Modify `assets/custom.css` for visual customization
- Update `components.py` for layout changes
- Customize color schemes and responsive breakpoints

### AI Behavior
- Adjust recommendation weights in `ai_model.py`
- Modify keyword extraction parameters
- Fine-tune similarity algorithms

## 🧪 Testing

### Sample Data
The application includes fallback sample data when the News API is unavailable:
- Automatically switches to cached content
- Provides sample articles for development
- Maintains functionality during API outages

### Development Mode
- Enable debug mode for detailed error messages
- Use sample data by setting `ALWAYS_USE_SAMPLE = True`
- Monitor console logs for troubleshooting

## 🔒 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: Werkzeug security for password protection
- **CORS Protection**: Configured for frontend-backend communication
- **Input Validation**: Pydantic models for API validation
- **Privacy Controls**: Transparent data usage with user consent

## 📈 Performance

### Caching
- **News Caching**: Reduces API calls with intelligent caching
- **Session Storage**: Efficient frontend state management
- **Background Updates**: Scheduled news fetching reduces load times

### Optimization
- **Pagination**: Efficient data loading
- **Lazy Loading**: Articles loaded as needed
- **Database Indexing**: Optimized MongoDB queries

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🆘 Support

### Common Issues
- **API Key Issues**: Ensure your News API key is valid and not rate-limited
- **MongoDB Connection**: Verify MongoDB is running and connection string is correct
- **Port Conflicts**: Ensure ports 8000 and 8050 are available

### Getting Help
- Check the console logs for detailed error messages
- Verify all environment variables are set correctly
- Ensure all dependencies are installed with correct versions

## 🚀 Future Enhancements

- **Real-time Notifications**: Push notifications for breaking news
- **Social Features**: Share articles and see what friends are reading  
- **Advanced Analytics**: Detailed reading statistics and insights
- **Mobile App**: Native iOS and Android applications
- **Multilingual Support**: Content in multiple languages
- **RSS Integration**: Import from custom RSS feeds

## 📊 Technology Stack

**Frontend**: Dash, Bootstrap, JavaScript  
**Backend**: FastAPI, Python  
**Database**: MongoDB  
**AI/ML**: scikit-learn, NLTK  
**Authentication**: JWT  
**Deployment**: Docker-ready  
**APIs**: News API, RESTful architecture

---

*Built with ❤️ for transparent and intelligent news consumption*
