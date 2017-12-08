# Battle of the Bands

This is the repository of the files I used to generate the data for the [Battle of the Bands](https://docs.google.com/presentation/d/1lXEzi7NIYbsydYZy2mrTK3nFwHgjYiBCRVEGXMKF58A/edit?usp=sharing) presentation at [MK Geek Night 23](https://mkgeeknight.co.uk/events/mkgn-23) in December 2017. 

Please take this code and do your own analysis. Which is better, _Oasis_ or _Blur_? _The Smiths_ or _The Cure_? Please [let me know](https://twitter.com/neilnjae) what you find out!


And I apologies for the shocking state of the code in these notebooks: it's stuff I cobbled together for my own use.

## Tools

There are quite a few tools used in the preparation of this data. They are:

* [Python 3](https://www.python.org)
* [Jupyter Notebooks](https://jupyter.org/), a just awesome of doing exploratory programming and development
* [Pandas](https://pandas.pydata.org/) for data wrangling
* [SciPy](https://www.scipy.org/) for the convex hull calculation
* [NumPy](http://www.numpy.org/) required for Panads and SciPy
* [Matplotlib](https://matplotlib.org/) for data visualisation
* [MongoDB](https://www.mongodb.com/) and [PyMongo](https://api.mongodb.com/python/current/) for data persistence
* [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) for parsing HTML

(You may want to install [Anaconda] to get most of these in one bundle.)

## Data sources

All the data comes from publicly-accessible sources, generally via APIs. You'll need to register with these providers before you can get the data. 

* Music data came from [Spotify](https://developer.spotify.com/)
* Lyrics came from [Genius](https://genius.com/developers)
* Sentiment analysis came from [Text Processing](http://text-processing.com/docs/sentiment.html) and the [NRC word-emotion lexicon](http://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm)

Note that the NRC sentiment lexicon isn't available for download, but you'll have to email the creator. 

You can obtain a cache of what I gathered in the `dump` directory of this repo. Use `mongorestore` to recover the data. 

## Use

The simplest and best-documented notebooks are the [Beatles vs Stones: gather data](beatles-vs-stones-gather-data.ipynb) and [Beatles vs Stones: analysis](beatles-vs-stones-analysis.ipynb) notebooks. Once you've seen those, take a look at [generic data gathering](multi-artist-gather-data.ipynb) and [generic data analysis](multi-artist-analysis.ipynb) to do the wider analysis. In particular, the [generic data analysis](multi-artist-analysis.ipynb) notebook does the convex hull calculation that generated the figures in the presentation.

You'll also need to run through the [Tag lyrics with emotions](/tag-lyrics-with-emotions.ipynb) notebook if you're using the NRC sentiment corpus. 
