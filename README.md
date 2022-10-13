# Homework2

## Required Libraries

In order to run this notebook you will need pandas which is not included in the standard python library 

This can be installed by using 
`pip install pandas`

## Data Descriptions
There are two CSV files located in the data folder of this repository. Inside is politicians_by_country_SEPT2022.csv which is atable containing politicians names, their associated Wikipedia URL and their respective country. The second table is population_by_country_2022.csv which is a table of country names and thair population in millions. Along with just countries there are also countries associated regions assorted heirchicaly by indication through being capitialized. In the first rows you will notice WORLD, followed by AFRICA followed by NORTHERN AFRICA. This represents how Northern Africa is in Africa and Africa in the world.

The outputs of this script will be two files by the name of wp_politicians_by_country.csv which will contain information about politicians, the revision id of their article, thearticle quality, the country they are in, its region, and its population as well. The other file named
wp_countries-no_match.txt is a list of all of the countries that arent included in this analysis because data couldnt be found for them.

## Resources
- [WP10 resource](https://meta.wikimedia.org/wiki/Objective_Revision_Evaluation_Service/wp10): information about the model used in this analysis


## Research Implications

During this project I had learned of some different pandas functions that made cleaning up the data a bit easier. I had also learned more about the process of Wikipedia article rating. It makes sense that the natural next step of a platform the size of Wikipedia would be to use some sort of model to perform content moderation of some capacity, but I was unaware of the amount of research that actually goes into this field. I had looked into each of the models before running the scraping query and I landed on wp10 because the page had featured metrics on the models performance. I thought this would be a good model to chose because whatever results I got from the analysis, I figured some baseline results would help to ease any of the suprises in the results. Apparently the model under the hood is just a random forest so nothing crazy under the hood. I had noticed another model which used a gradient boosting tree, however I valued the documentation of the wp10 model over the potential gains that might or might not be realized from another model.

Through the analysis, I had found that the lineup of countries with the most quality articles to be a bit suprising. For example the highest results were Barbados, Andorra, Federated States of Micronesia and Antigua and Barbuda. I had definitley expected the United States to be at the top of the list just because the end of lecture demo. This makes me wonder about which factors the model had deemed most important. It does make sense that on the English Wikipedia that there would be more high quality articles of US politicians than other countries. This makes me wonder if they had tried to correct for this bias or if this is just simply the result of the population normalization. Also it could just be that the initial web scrape sampled US articles that are lower of lower quality. Like in the last questions I had realized that North America had no featured articles which seemed suspicious and seemed like some of the underlying input data might be to blame.

- What biases did you expect to find in the data (before you started working with it), and why?

When starting the project I expected to see countries like the US at the highest unmber of quality articles per capita. This is because in class when the idea of the assignment was being touted, the example given was how a non-president had a featured article where as the president of France only had a B rating. For this reason I was expecting to see a lot of Western European countries as well as North American countries at the top of the number of featured articles per capita.

- Can you think of a realistic data science research situation where using these data (to train a model, perform a hypothesis-driven research,   or make business decisions) might still be appropriate and useful, despite its inherent limitations and biases?

For database purposes or knowledge graph purposes, wikipedia is the best open source of information that you can access. If all the model is doing is relating queries to answers then I beleive that this would be fine. Its the infromation that would have been on Wikipedia anyways so its not like you are manipulating it at all. Some of the only things I can think of are maybe bias in popularity of articles that have similar names. Like if two famous people have the same name then it will probably be optimized to return the more popular one. For this I see no problem. 

- How might a researcher supplement or transform this dataset to potentially correct for the limitations/biases you observed?

If there is an imbalance in the number of articles from certian regions, for example there being a ton of articles for US politicians but not many for a country like Zambia. To help could you normalize the number of articles such that the articles per capita in the training set is equal for all countries.
