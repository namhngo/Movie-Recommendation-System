# Movie Recommendation System

A content-based movie recommendation system that uses machine learning to suggest movies based on similarity scores. The system analyzes movie features such as genres, keywords, cast, director, and tagline to find movies with similar characteristics.

## Features

- **Content-Based Filtering**: Recommends movies based on movie features rather than user ratings
- **TF-IDF Vectorization**: Converts textual features into numerical vectors for analysis
- **Cosine Similarity**: Calculates similarity scores between movies
- **Fuzzy String Matching**: Handles typos and variations in movie title searches
- **Interactive Jupyter Notebook**: User-friendly interface with search widgets
- **Top 30 Recommendations**: Returns the most similar movies for any given input

## Dataset

The system uses a comprehensive movie dataset (`movies.csv`) containing 4,803 movies with 24 features including:
- **Genres**: Action, Adventure, Comedy, Drama, etc.
- **Keywords**: Plot-related keywords and themes
- **Cast**: Main actors and actresses
- **Director**: Movie director information
- **Tagline**: Movie taglines and descriptions
- **Metadata**: Budget, revenue, runtime, ratings, and more

## Technology Stack

- **Python 3.x**
- **pandas**: Data manipulation and analysis
- **NumPy**: Numerical computations
- **scikit-learn**: Machine learning algorithms
  - TfidfVectorizer for text feature extraction
  - cosine_similarity for similarity calculations
- **difflib**: Fuzzy string matching for movie titles
- **ipywidgets**: Interactive Jupyter notebook widgets
- **IPython**: Enhanced interactive Python shell

## Installation

1. Clone the repository:
```bash
git clone https://github.com/namhngo/Movie-Recommendation-System.git
cd Movie-Recommendation-System
```

2. Install required dependencies:
```bash
pip install pandas numpy scikit-learn ipywidgets
```

3. Launch Jupyter Notebook:
```bash
jupyter notebook movie_rcm.ipynb
```

## Usage

### Method 1: Interactive Jupyter Widget
1. Open the notebook and run all cells
2. Use the interactive text widget that appears
3. Type a movie name in the search box
4. Get instant recommendations as you type

### Method 2: Function Call
```python
# Search for movie recommendations
recommended_movies = search_movies("Spider-Man")
print(recommended_movies[:10])  # Top 10 recommendations
```

### Example Output
```
Movies recommended for you:

1. Spider-Man
2. Spider-Man 3
3. Spider-Man 2
4. The Notebook
5. Seabiscuit
6. Clerks II
7. The Ice Storm
8. Oz: The Great and Powerful
9. Horrible Bosses
10. The Count of Monte Cristo
```

## How It Works

1. **Data Preprocessing**: 
   - Handles missing values by filling with empty strings
   - Combines relevant features (genres, keywords, tagline, cast, director)

2. **Feature Engineering**:
   - Uses TF-IDF (Term Frequency-Inverse Document Frequency) vectorization
   - Converts combined text features into numerical vectors

3. **Similarity Calculation**:
   - Computes cosine similarity between all movie vectors
   - Creates a similarity matrix for the entire dataset

4. **Recommendation Generation**:
   - Finds closest movie title match using fuzzy string matching
   - Retrieves similarity scores for the matched movie
   - Sorts movies by similarity score in descending order
   - Returns top recommendations

## Project Structure

```
movie_rcm/
├── README.md
├── movie_rcm.ipynb          # Main Jupyter notebook
├── movies.csv               # Movie dataset (4,803 movies)
└── .git/                    # Git repository files
```

## Algorithm Details

The recommendation system uses **content-based filtering** with the following steps:

1. **Text Processing**: Combines genres, keywords, tagline, cast, and director into a single feature string
2. **TF-IDF Vectorization**: Transforms text data into numerical feature vectors
3. **Cosine Similarity**: Measures similarity between movie vectors using the formula:
   ```
   similarity = cos(θ) = (A · B) / (||A|| × ||B||)
   ```
4. **Ranking**: Sorts movies by similarity scores and returns top matches

## Future Enhancements

- [ ] Add collaborative filtering for hybrid recommendations
- [ ] Include user rating predictions
- [ ] Implement web interface using Flask/Streamlit
- [ ] Add more sophisticated NLP preprocessing
- [ ] Include movie poster visualization
- [ ] Add genre-specific filtering options
- [ ] Implement caching for faster recommendations

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- Dataset provided by The Movie Database (TMDb)
- Built using scikit-learn's machine learning algorithms
- Inspired by content-based recommendation system research