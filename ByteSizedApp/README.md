# Byte-Sized Business Boost

## Project Overview

Byte-Sized Business Boost is a desktop application designed to help users discover and support small, local businesses in their community. Built for the 2025-2026 FBLA Coding & Programming competition, this application provides a comprehensive platform for browsing businesses, leaving reviews, favoriting establishments, and discovering special deals.

## Features

### Core Requirements (All Implemented)

✅ **Sorting by Category**: Browse businesses across 6 categories:
   - Food & Dining (coffee shops, cafes, family-owned restaurants)
   - Retail (bodegas, convenience stores, clothing stores)
   - Services (barber shops, auto repair, dry cleaners)
   - Health & Wellness (chiropractors, dental offices, yoga studios)
   - Specialty Shops (tech repair, home decor, arts & crafts)
   - Local Professionals (photographers, attorneys, physical therapists)

✅ **Reviews & Ratings**: 
   - 5-star rating system for businesses
   - Written review text (optional)
   - Automatic calculation of average ratings
   - Businesses sorted by highest ratings

✅ **Favorites/Bookmarking**:
   - Bookmark button to favorite businesses
   - Visual indicator (yellow highlight) for favorited businesses
   - Filter to show only favorite businesses

✅ **Special Deals & Coupons**:
   - Display active deals for businesses
   - Deal expiration dates
   - Filter to show only businesses with deals

✅ **Bot Verification**:
   - CAPTCHA system on login and signup
   - Math-based verification to prevent automated account creation

✅ **User Accounts**:
   - Secure account creation with email and password
   - Login system with validation
   - User-specific favorites tracking

## Technology Stack

### Language Selection: Java with JavaFX

**Why Java?**
- **Object-Oriented Design**: Java's strong OOP principles enable clean, modular code architecture
- **Type Safety**: Strong typing helps prevent runtime errors and improves code reliability
- **Mature Ecosystem**: Extensive standard library and third-party support
- **Cross-Platform**: Runs on Windows, macOS, and Linux without modification
- **Industry Standard**: Widely used in enterprise applications, demonstrating professional development practices

**Why JavaFX?**
- **Modern UI Framework**: Provides a contemporary alternative to Swing with better styling capabilities
- **FXML Declarative UI**: Separates UI design from business logic, improving maintainability
- **Rich Controls**: Comprehensive set of UI components (ListView, ToggleButtons, etc.)
- **Scene Builder Compatible**: Visual design tools available for rapid UI development
- **Event-Driven Architecture**: Well-suited for interactive desktop applications

### Dependencies

- **JavaFX 21.0.2**: UI framework for desktop application
- **Gson 2.10.1**: JSON serialization for data persistence
- **Java 11+**: Required runtime environment

## Project Structure

```
ByteSizedApp/
├── src/
│   ├── Main.java                 # Application entry point
│   ├── controller/               # FXML controllers
│   │   ├── LoginController.java
│   │   ├── SignupController.java
│   │   └── MainController.java
│   ├── model/                    # Data models
│   │   ├── User.java
│   │   ├── Business.java
│   │   ├── Review.java
│   │   └── Deal.java
│   ├── util/                     # Utility classes
│   │   ├── DataManager.java      # Central data management
│   │   ├── ValidationUtil.java   # Input validation
│   │   └── CaptchaUtil.java      # CAPTCHA generation
│   └── view/                     # FXML UI files
│       ├── login.fxml
│       ├── signup.fxml
│       └── main.fxml
├── data/                         # JSON data storage
│   ├── users.json
│   ├── businesses.json
│   ├── reviews.json
│   └── deals.json
└── pom.xml                       # Maven configuration
```

## Installation & Setup

### Prerequisites
- Java 11 or higher
- Maven 3.6 or higher

### Building the Project

1. **Clone or download the project**

2. **Navigate to the project directory**
   ```bash
   cd ByteSizedApp
   ```

3. **Build with Maven**
   ```bash
   mvn clean install
   ```

4. **Run the application**
   ```bash
   mvn javafx:run
   ```

   Or compile and run manually:
   ```bash
   javac -cp "target/classes:target/dependency/*" src/**/*.java
   java -cp "target/classes:target/dependency/*" Main
   ```

## Usage Guide

### Creating an Account

1. Launch the application
2. Click "Sign Up" on the login screen
3. Enter your full name, email, and password
4. Solve the CAPTCHA challenge
5. Click "Create Account"

**Password Requirements:**
- At least 8 characters
- At least one uppercase letter
- At least one number

### Logging In

1. Enter your email and password
2. Solve the CAPTCHA challenge
3. Click "Login"

### Using the Main Application

1. **Browse by Category**: Click category tabs at the top to filter businesses
2. **View Details**: Click on a business in the list to see full details
3. **Favorite Businesses**: Click the "Favorite" button to bookmark a business
4. **Filter Options**:
   - Check "Favorites Only" to see only your favorited businesses
   - Check "Deals Only" to see only businesses with active deals
5. **Leave Reviews**:
   - Select a business
   - Choose a star rating (1-5)
   - Optionally write a review
   - Click "Submit Review"
6. **View Deals**: Active deals are displayed in the business details panel

## Code Quality Features

### Modular Design
- **Separation of Concerns**: Controllers handle UI logic, models represent data, utilities provide reusable functions
- **Singleton Pattern**: DataManager ensures single instance for consistent data access
- **MVC Architecture**: Model-View-Controller pattern separates UI from business logic

### Code Comments
- Comprehensive JavaDoc comments on all classes and public methods
- Inline comments explaining complex logic
- Clear method documentation with parameter and return descriptions

### Input Validation
- **Email Validation**: Regex pattern matching for proper email format
- **Password Strength**: Validates length, uppercase, and numeric requirements
- **CAPTCHA Verification**: Prevents automated bot activity
- **Rating Validation**: Ensures star ratings are within valid range (1-5)
- **Empty Field Checks**: Prevents submission of incomplete forms

### Error Handling
- Try-catch blocks for file I/O operations
- User-friendly error messages
- Graceful degradation when data files are missing

### Data Structures
- **Lists**: Used for businesses, users, reviews, and deals
- **Sets**: Used for efficient favorite business tracking (O(1) lookup)
- **ObservableList**: JavaFX collections for reactive UI updates
- **Proper Variable Scope**: Instance variables for state, local variables for temporary data

## Data Persistence

The application uses JSON files for data storage:
- `data/users.json`: User account information
- `data/businesses.json`: Business listings
- `data/reviews.json`: User reviews and ratings
- `data/deals.json`: Active deals and coupons

Data is automatically saved when users, reviews, or deals are added or modified.

## Accessibility Features

- Clear, readable fonts and sizing
- High contrast text colors
- Logical tab order for keyboard navigation
- Descriptive labels for all interactive elements
- Error messages displayed in red for visibility

## Future Enhancements (Time Permitting)

- Interactive map with business locations
- Responsive design for different screen sizes
- Search functionality
- Business owner account management
- Email notifications for new deals

## Copyright & Open Source

This project uses the following open-source libraries:
- **JavaFX**: OpenJDK project (GPL v2 with Classpath Exception)
- **Gson**: Apache 2.0 License

All code in this project is original work created for the FBLA Coding & Programming competition.

## Troubleshooting

### JavaFX Imports Not Working
- Ensure Maven dependencies are downloaded: `mvn clean install`
- Reload the Maven project in your IDE
- Verify JavaFX is in the classpath

### Application Won't Start
- Check Java version: `java -version` (must be 11+)
- Verify Maven build completed successfully
- Check that FXML files are in the correct directory

### Data Not Persisting
- Ensure the `data/` directory exists and is writable
- Check file permissions
- Verify JSON files are not corrupted

## Contact & Support

For questions about this project, please contact the development team.

---

**Developed for FBLA Coding & Programming Competition 2025-2026**
**Topic: Byte-Sized Business Boost**
