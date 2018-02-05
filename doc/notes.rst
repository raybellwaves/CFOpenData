.. _notes:

CrossFit open data is displayed at the URL:
https://games.crossfit.com/leaderboard/open/2017?division=2&region=0&scaled=0&sort=0&occupation=0&page=1

This Reddit post explains how to download data from the site:
https://www.reddit.com/r/crossfit/comments/5uikq8/2017_open_data_analysis/

To summarise: a page can be turned into a text file (or more accurately json 
(JavaScript Object Notation File) file) which contains information stored as arrays)

For example, the URL:
https://games.crossfit.com/leaderboard/open/2017?division=1&region=0&scaled=0&sort=0&occupation=0&page=1
shows the Men Rank 1 to Rank 49.
To obtain the json file of this the URL is:
https://games.crossfit.com/competitions/api/v1/competitions/open/2017/leaderboards?page=1&competition=1&year=2017&division=1&scaled=0&sort=0&fittest=1&fittest1=0&occupation=0

The key's I am interested in are::

    userid # 1 - number of athletes
    name # First and Last name
    divisionid # 1 is individual Men, 2 is individual Women, others are listed in the Reddit post
    scaled # 0 is Rx, 1 is Scaled
    
_______________________

TO DO

Crossfit converts time (duration) into a score by using total number of seconds
Keep the time and store it as a TimeDelta (e.g. ...)
Test writing a DataFrame with strings, integers and Time Delta's

Plot using Holoviews

Add percentile on plot. Test with googlesheet plot
