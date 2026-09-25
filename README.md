# whats-next-poc
Proof of concept for What's Next: demonstrates the core stack(Flask + pandas + NumPy) working together with the MovieLens dataset.

Environment: macOS 15.7.9, Python 3.13.9

## Setup
Clone and enter the repository: `git clone https://github.com/DylanTranTemple/whats-next-poc && cd whats-next-poc` 

Create and activate a virtual environment:

`python -m venv venv`

`source venv/bin/activate`

Install dependencies: `pip install -r requirements.txt`

Download the MovieLens ml-latest-small dataset: 

`curl -O https://files.grouplens.org/datasets/movielens/ml-latest-small.zip`

`unzip ml-latest-small.zip`

`mkdir -p data`

`mv ml-latest-small/ratings.csv ml-latest-small/movies.csv data/`

Start the server: `python poc.py`

## Test
`curl http://127.0.0.1:5000/movie/2571`

Should return the title, average rating, and rating count for The Matrix (movieId 2571).

## Evidence of Execution
(venv) (base) Mac:whats-next-poc dylantran$ python poc.py
 * Serving Flask app 'poc'
 * Debug mode: on
WARNING: This is a development server. Do not use it in a production deployment. Use a production WSGI server instead.
 * Running on http://127.0.0.1:5000
Press CTRL+C to quit
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 112-744-921

127.0.0.1 - - [23/Sep/2026 14:47:12] "GET /movie/2571 HTTP/1.1" 200 -

(venv) (base) Mac:whats-next-poc dylantran$ curl http://127.0.0.1:5000/movie/2571

{
  "average_rating": 4.192446043165468,
  "movieId": 2571,
  "num_ratings": 278,
  "title": "Matrix, The (1999)"
}

(venv) (base) Mac:whats-next-poc dylantran$