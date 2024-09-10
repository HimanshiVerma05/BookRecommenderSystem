
# Book Recommendation System using Collaborative Filtering

This is a book recommendation system built using collaborative filtering techniques. The system recommends books based on user ratings and the similarity between either books (item-item filtering) or users (user-user filtering).

## Table of Contents

- [About](#about)
- [Features](#features)
- [Technologies](#technologies)
- [Data Sources](#data-sources)
- [Installation](#installation)
- [Usage](#usage)
- [Files and Folders](#files-and-folders)
- [How It Works](#how-it-works)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## About

This project implements a book recommendation system that provides personalized recommendations to users based on their historical ratings. Collaborative filtering, a popular recommendation algorithm, is used to make predictions by analyzing user-item interactions.

## Features

- **Personalized recommendations** based on collaborative filtering (User-User & Item-Item)
- **Popular books** display on the homepage
- Ability to search for recommendations by entering a book name
- Flask web application with a user-friendly interface
- Preprocessed data and fast loading using `.pkl` files for efficient performance

## Technologies

This project uses the following tools and technologies:

- **Python**: Core programming language
- **Flask**: For building the web application
- **Pandas**: For data manipulation
- **Numpy**: For numerical operations
- **Pickle**: For saving and loading preprocessed data
- **Jinja2**: For HTML templating
- **Bootstrap**: For styling the front-end pages

## Data Sources

- **Books.csv**: Contains book metadata such as book ID, title, author, etc.
- **Users.csv**: Contains information about users.
- **Ratings.csv**: Contains user ratings for different books.

These CSV files are processed and saved into `.pkl` files for efficient data access within the web application.

## Installation

### 1. Clone the repository
   ```bash
   git clone https://github.com/HimanshiVerma05/BookRecommenderSystem.git
   cd book-recommender-system
   ```

### 2. Create and activate a virtual environment
   ```bash
   python -m venv venv
   # For Windows
   venv\Scripts\activate
   # For macOS/Linux
   source venv/bin/activate
   ```

### 3. Install required dependencies
   Install the dependencies listed in the `requirements.txt` file:
   ```bash
   pip install -r requirements.txt
   ```

### 4. Set up the environment
   If you're running the Flask app locally, set the Flask environment variable:
   ```bash
   # For Windows
   set FLASK_APP=app.py
   # For macOS/Linux
   export FLASK_APP=app.py
   ```

### 5. Start the Flask application
   Run the Flask application locally:
   ```bash
   flask run
   ```

### 6. Access the app
   Open your browser and go to `http://127.0.0.1:5000/` to interact with the recommendation system.

## Usage

1. **Home Page**: The homepage displays the top 50 most popular books, which are precomputed and loaded from `popular.pkl`.
2. **Recommendation Page**: Navigate to the "Recommend" page, input the name of a book, and receive personalized recommendations.
3. **Backend**: The backend loads preprocessed data (books, ratings, similarity scores) from `.pkl` files to generate recommendations.

## Files and Folders

- **app.py**: Main Python file that defines the Flask routes and loads data from `.pkl` files.
- **templates/**: Contains the HTML templates (index.html and recommend.html) for rendering the UI using Jinja2.
  - `index.html`: Displays the top 50 books.
  - `recommend.html`: Allows users to search for book recommendations.
- **static/**: Folder for static assets like CSS, images, etc.
- **Books.csv**, **Ratings.csv**, **Users.csv**: Raw data files used for building the recommendation system.
- **books.pkl**, **similarity_scores.pkl**, **pt.pkl**: Preprocessed data files for faster loading and recommendation generation.
- **requirements.txt**: Contains the list of dependencies required to run the project.

## How It Works

1. **Data Preprocessing**: The book, user, and rating data are loaded from CSV files and cleaned. Missing values are handled, and similarity scores are computed based on user-item interactions.
   
2. **Collaborative Filtering**: 
   - **User-User Collaborative Filtering**: Recommends books to a user based on the similarity to other users' preferences.
   - **Item-Item Collaborative Filtering**: Recommends similar books based on the similarity between books (e.g., books rated highly by the same users).

3. **Pickle Serialization**: The preprocessed data (books, ratings, and similarity scores) are saved in `.pkl` files to avoid reprocessing the data each time the app is run.

4. **Flask Web Application**: The Flask app serves two primary pages: the homepage showing popular books and the recommendation page, where users can input a book and get recommendations.

## Future Enhancements

- Add support for **content-based filtering**.
- Integrate a **user login system** to track individual users' reading histories.
- Improve the recommendation algorithm with **hybrid filtering** (combining collaborative filtering with content-based techniques).
- Add **more dynamic user interaction features**, such as rating or reviewing books directly in the app.

## References
- Special thanks to Campusx tutorial - https://www.youtube.com/watch?v=1YoD0fg3_EM
- Dataset from - https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset
