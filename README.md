# BGG Data Fetcher

This script will fetch items data from BoardGameGeek API and store the data in a CSV file. 

I updated the [preivous script](https://www.drangovski.com/article/boardgamegeek-board-games-data-fetching). Since the API response is in XML format and since there is no endpoint to fetch all items at once, the previous script would loop through a provided IDs range, making calls one by one for each item. That's not optimal, it takes long time for larger range of IDs (currently the highest number of items (IDs) available on BGG goes as high as 400k+) and the results may not be reliable. Therefore, with some modifications in this script, more item IDs will be added as parameter value to a single request url, and with that, a single response will return multiple items (~800 was the highest number that a single response returned back. BGG may eventually change this later; you can easily tweak `batch_size` in order to adjust if needed).

The information fetched and stored for each board game is the following:

`name`, `game_id`, `type`, `rating`, `weight`, `year_published`, `min_players`, `max_players`, `min_play_time`, `max_pay_time`, `min_age`, `owned_by`, `categories`, `mechanics`, `designers`, `artists` and `publishers`.
