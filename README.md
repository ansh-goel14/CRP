# Cooking Recipe Portal 🍳

![MySQL](https://img.shields.io/badge/MySQL-8.0+-blue.svg)
![Database](https://img.shields.io/badge/Database-Management-orange.svg)
![Recipes](https://img.shields.io/badge/Recipes-44+-green.svg)
![Categories](https://img.shields.io/badge/Categories-7-red.svg)
![License](https://img.shields.io/badge/License-MIT-lightgrey.svg)

A comprehensive **MySQL database management system** for a cooking recipe portal that organizes recipes by categories, manages user interactions, provides video tutorials, and tracks ingredients. This project demonstrates advanced database design with normalized tables, user management, and comprehensive recipe categorization.

##  Project Overview

This database-driven cooking portal provides a complete solution for:

- **Recipe Management**: 44+ diverse recipes across multiple cuisines
- **Category Organization**: 7 distinct food categories with specialized tables
- **User System**: User registration, reviews, and personalized recipe tracking
- **Video Integration**: YouTube tutorial links for each recipe
- **Ingredient Tracking**: Detailed ingredient lists for all recipes
- **Rating System**: Community-driven recipe ratings (8-10 scale)
- **Personalized Tables**: Individual user recipe tracking with opacity-based favorites

## 🗄️ Database Architecture

### Core Database Structure

```sql
CREATE DATABASE Cooking_Portal;
```

### 📊 Database Statistics
- **Total Tables**: 23 tables
- **Recipe Entries**: 44 unique recipes
- **Categories**: 7 specialized cuisine categories
- **Users**: 8 registered users with reviews
- **Video Tutorials**: 44 YouTube integration links

## 🏗️ Table Structure & Relationships

### 1. Master Recipe Table
```sql
CREATE TABLE Recipe(
    Recipe_id INT PRIMARY KEY,
    Recipe_name VARCHAR(50),
    Recipe_type VARCHAR(50),
    Description VARCHAR(1000)
);
```
**Purpose**: Central repository for all recipes with unique IDs and descriptions

### 2. Category Tables (7 Specialized Cuisines)

#### North Indian Cuisine
- **Specialties**: Dal Makhani, Shahi Paneer, Malai Kofta
- **Focus**: Traditional North Indian vegetarian dishes
- **Rating Range**: 9-10/10

#### South Indian Cuisine  
- **Specialties**: Masala Dosa, Uttapam, Idli Vada Sambhar
- **Focus**: Authentic South Indian breakfast and main course items
- **Rating Range**: 9-10/10

#### Non-Vegetarian Section
- **Specialties**: Chicken Tikka, Mutton Roast, Chicken Biryani
- **Focus**: Premium non-vegetarian dishes
- **Rating Range**: 9-10/10

#### Italian Cuisine
- **Specialties**: Margherita Pizza, Mushroom Risotto, Bruschetta
- **Focus**: Italian and Indo-Italian fusion dishes
- **Rating Range**: 8-10/10

#### Snacks Category
- **Specialties**: Momos, Spring Rolls, Chicken Wings
- **Focus**: Quick bites and appetizers
- **Rating Range**: 9-10/10

#### Desserts Collection
- **Specialties**: Gulab Jamun, Rasmalai, Kulfi
- **Focus**: Traditional Indian sweets and desserts
- **Rating Range**: 9-10/10

#### Beverages Menu
- **Specialties**: Badam Milk, Mint Mojito, Cold Coffee
- **Focus**: Refreshing drinks and traditional beverages
- **Rating Range**: 9-10/10

### 3. User Management System

#### User Registration Table
```sql
CREATE TABLE User(
    User_Id INT PRIMARY KEY,
    User_Name VARCHAR(30),
    Phone_Number DECIMAL(10),
    Email_id VARCHAR(30),
    Review VARCHAR(1000)
);
```

#### Registered Users Portfolio
- **Amit Trivedi**: "This site is very useful for beginners."
- **Adhyaan Kumar**: "Keep up the good work."
- **Shiela Gupta**: "Awesome work man!"
- **Zaran Sheik**: "Great work dude. Keep it up!"
- **Priya Goel**: "Finally got the website which i was searching for!"
- **Krish Seth**: "Yo! Good workk!!!"
- **Kat Singhania**: "I am lovinn this site !!!!!"
- **Akshat Bhandari**: "Oh gosh! U are Fascinating"

### 4. Personalized User Tables

Each user has a dedicated table for personalized recipe tracking:
- **Individual Tracking**: Personal recipe opacity settings
- **Favorites System**: 0 opacity indicates favorite status
- **Customization**: User-specific recipe modifications

### 5. Rich Media Integration

#### Video Tutorials Table
```sql
CREATE TABLE Video_Tutorials(
    Recipe_id INT PRIMARY KEY,
    Recipe_Name VARCHAR(30),
    Video_Link VARCHAR(1000)
);
```
- **Complete Coverage**: YouTube tutorials for all 44 recipes
- **Professional Content**: Curated cooking demonstrations
- **Easy Access**: Direct links integrated with recipe data

#### Ingredient Management
```sql
CREATE TABLE Ingredient(
    Recipe_Id INT PRIMARY KEY,
    Recipe_Name VARCHAR(30),
    Recipe_Type VARCHAR(20),
    Ing_Name VARCHAR(1000)
);
```
- **Detailed Lists**: Comprehensive ingredient specifications
- **Quantity Information**: Bowl measurements, cup measurements
- **Special Instructions**: Cooking tips embedded in ingredient lists

## 🍽️ Featured Recipe Categories

### 🌶️ North Indian Delicacies
| Recipe | Type | Rating | Key Ingredients |
|--------|------|--------|----------------|
| Dal Makhani | Vegetarian | 9/10 | 2 Bowl Lentils, 1L Milk, Spices |
| Shahi Paneer | Vegetarian | 9/10 | 500g Paneer, Tomatoes, Spices |
| Malai Kofta | Vegetarian | 9/10 | Potatoes, Tomatoes, Milk |

### 🥥 South Indian Specialties
| Recipe | Type | Rating | Key Ingredients |
|--------|------|--------|----------------|
| Masala Dosa | Vegetarian | 9/10 | 3 Bowl Lentils, Rice, Potatoes |
| Uttapam | Vegetarian | 9/10 | 4 Bowl Lentils, Vegetables |
| Idli Vada Sambhar | Vegetarian | 10/10 | 6 Bowl Lentils, Rice, Coconut Oil |

### 🍖 Premium Non-Vegetarian
| Recipe | Type | Rating | Key Ingredients |
|--------|------|--------|----------------|
| Chicken Tikka | Non-Veg | 9/10 | Deep Fried Chicken, Cream, Spices |
| Mutton Korma | Non-Veg | 10/10 | Creamy Mutton, Spices, Onions |
| Chicken Biryani | Non-Veg | 9/10 | Basmati Rice, Chicken, Spices |

### 🍕 Italian Fusion
| Recipe | Type | Rating | Key Ingredients |
|--------|------|--------|----------------|
| Margherita Pizza | Vegetarian | 9/10 | Pizza Dough, Cheese, Olives |
| Mushroom Risotto | Vegetarian | 9/10 | Grilled Mushrooms, Rice, White Wine |
| Bruschetta | Vegetarian | 10/10 | Bread, Mozzarella, Vegetables |

## 📈 Database Analytics

### Recipe Distribution
```sql
CREATE TABLE Proportion(
    Category_Id INT PRIMARY KEY,
    Recipe_Type VARCHAR(30),
    Count INT
);
```

| Category | Recipe Count | Percentage |
|----------|--------------|------------|
| North Indian | 7 recipes | 15.9% |
| South Indian | 7 recipes | 15.9% |
| Non-Vegetarian | 7 recipes | 15.9% |
| Italian | 7 recipes | 15.9% |
| Snacks | 6 recipes | 13.6% |
| Desserts | 6 recipes | 13.6% |
| Beverages | 5 recipes | 11.4% |

### User Engagement Metrics
- **User Reviews**: 100% positive feedback
- **Average Rating**: 9.2/10 across all recipes
- **Video Integration**: 100% tutorial coverage
- **Personalization**: Individual user tables for customization

## 🚀 Key Features

### Advanced Database Design
- **Normalized Structure**: Minimized data redundancy
- **Referential Integrity**: Proper primary key relationships
- **Scalable Architecture**: Easy addition of new recipes and users
- **Category Optimization**: Specialized tables for efficient querying

### User Experience Features
- **Comprehensive Search**: Multi-table recipe discovery
- **Rating System**: Community-driven quality assessment
- **Video Learning**: Visual cooking instruction integration
- **Personal Tracking**: Individual user recipe management

### Content Management
- **Rich Descriptions**: Detailed recipe backgrounds and origins
- **Ingredient Precision**: Exact measurements and specifications
- **Cultural Context**: Regional and international cuisine representation
- **Quality Curation**: High-rated recipes (8+ rating minimum)

## 💾 Database Operations

### Sample Queries

#### Find All Vegetarian Recipes
```sql
SELECT Recipe_name, Description, Rating 
FROM Recipe r
JOIN North_Indian ni ON r.Recipe_id = ni.Recipe_id
WHERE Recipe_type = 'Vegetarian'
ORDER BY Rating DESC;
```

#### User Recipe Preferences
```sql
SELECT u.User_Name, u.Review, COUNT(*) as Recipe_Count
FROM User u
JOIN Amit_Trivedi at ON u.User_Id = at.Recipe_id
WHERE at.Opacity = 0
GROUP BY u.User_Id;
```

#### Category Popularity Analysis
```sql
SELECT Recipe_Type, AVG(Rating) as Avg_Rating, COUNT(*) as Total_Recipes
FROM (
    SELECT Recipe_Type, Rating FROM North_Indian
    UNION ALL
    SELECT Recipe_Type, Rating FROM South_Indian
    UNION ALL
    SELECT Recipe_Type, Rating FROM Non_Vegetarian_Section
) AS combined_recipes
GROUP BY Recipe_Type
ORDER BY Avg_Rating DESC;
```

## 📊 Technical Specifications

### Database Configuration
- **Engine**: MySQL 8.0+
- **Character Set**: UTF8 for international cuisine names
- **Storage**: Optimized for read-heavy operations
- **Indexing**: Primary keys on all tables for fast lookups

### Table Relationships
- **One-to-Many**: Recipe to Category mapping
- **One-to-One**: Recipe to Video Tutorial linking
- **Many-to-Many**: User to Recipe preferences (via individual tables)
- **Hierarchical**: Category to Recipe specialization

### Data Integrity Features
- **Primary Keys**: Unique identification for all records
- **Data Types**: Optimized field types (VARCHAR, INT, DECIMAL)
- **Constraints**: Proper field length limitations
- **Validation**: Rating ranges (8-10) enforcement

## 🔧 Setup & Installation

### Prerequisites
```sql
-- MySQL Server 8.0+
-- Database Administration Tool (phpMyAdmin, MySQL Workbench)
-- Minimum 50MB storage space
```

### Database Creation
```sql
-- Create the main database
CREATE DATABASE Cooking_Portal;
USE Cooking_Portal;

-- Execute all table creation scripts
-- Import sample data (44 recipes, 8 users)
-- Verify table relationships
```

### Verification Query
```sql
SELECT COUNT(*) FROM information_schema.tables 
WHERE table_schema = 'Cooking_Portal';
-- Should return 23 tables
```

## 📱 Integration Possibilities

### Web Application Framework
- **Frontend**: HTML/CSS with dynamic recipe cards
- **Backend**: PHP/Python for database connectivity
- **API**: RESTful services for mobile app integration
- **Search**: Full-text search across recipes and ingredients

### Mobile App Features
- **Recipe Browser**: Category-wise recipe exploration
- **Video Player**: Embedded YouTube tutorial playback
- **Shopping List**: Automatic ingredient list generation
- **User Reviews**: Community feedback system

### Business Intelligence
- **Recipe Analytics**: Popular cuisine trends
- **User Behavior**: Preference pattern analysis
- **Content Optimization**: Rating-based recipe promotion
- **Performance Metrics**: Database query optimization

## 🤝 Contributing

Areas for expansion:

### Database Enhancements
- **Recipe Difficulty**: Skill level classification (Beginner, Intermediate, Expert)
- **Cooking Time**: Preparation and cooking duration tracking
- **Nutritional Data**: Calorie and nutrition information integration
- **Seasonal Recipes**: Seasonal availability and recommendations

### Feature Additions
- **Recipe Comments**: User discussion threads for each recipe
- **Photo Gallery**: Multiple images per recipe
- **Recipe Variations**: Alternative ingredient suggestions
- **Social Sharing**: Integration with social media platforms

## 📚 Use Cases

### Educational Applications
- **Culinary Schools**: Recipe database for cooking courses
- **Cultural Studies**: Regional cuisine exploration
- **Nutrition Education**: Healthy cooking demonstrations
- **Language Learning**: Multilingual recipe descriptions

### Commercial Applications
- **Restaurant Management**: Menu item database
- **Food Delivery Apps**: Recipe-based ordering system
- **Cooking Shows**: Content management for cooking programs
- **Publishing**: Cookbook database management

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🏆 Acknowledgments

- **Cultural Cuisine Experts**: For authentic recipe validation
- **Video Content Creators**: YouTube cooking channel partnerships
- **User Community**: Active feedback and recipe testing
- **Database Design Principles**: Following MySQL best practices for scalable architecture

---

**Keywords**: MySQL Database, Recipe Management, Cooking Portal, Database Design, Food Categories, User Management, Video Integration, Ingredient Tracking, Rating System, Culinary Database
