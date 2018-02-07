.. _notes:

CrossFit open data is displayed online here (1_).

This Reddit_ post explains how to download data from the site.

To summarise: a page can be turned into a text file (or more accurately json 
(JavaScript Object Notation File) file) which contains information stored as arrays).

For example, the URL_ shows the Men Rank 1 to Rank 49. This can be converted to a json file using this url (2_).

The key's I am interested in are::

    userid # 1 - number of athletes
    name # First and Last name
    divisionid # 1 is individual Men, 2 is individual Women, others are listed in the Reddit post
    scaled # 0 is Rx, 1 is Scaled
    
_______________________

TO DO

Workout why woman's score is showing random names at the start (first 27 names) and delete these.

Crossfit converts time (duration) into a score by using total number of seconds
Keep the time and store it as a TimeDelta (e.g. ...)
Test writing a DataFrame with strings, integers and Time Delta's

Plot using Holoviews_
Distribution plots using seaborn_

Add percentile on plot. Test with googlesheet plot



Long term TO DO (AKA will never do)

EVA of workouts to workout physical limits

.. _1: https://games.crossfit.com/leaderboard/open/2017?division=1&region=0&scaled=0&sort=0&occupation=0&page=1
.. _Reddit: https://www.reddit.com/r/crossfit/comments/5uikq8/2017_open_data_analysis/
.. _URL: https://games.crossfit.com/leaderboard/open/2017?division=1&region=0&scaled=0&sort=0&occupation=0&page=1
.. _2: https://games.crossfit.com/competitions/api/v1/competitions/open/2017/leaderboards?page=1&competition=1&year=2017&division=1&scaled=0&sort=0&fittest=1&fittest1=0&occupation=0
.. _Holoviews: https://github.com/ioam/holoviews
.. _seaborn: https://github.com/mwaskom/seaborn
