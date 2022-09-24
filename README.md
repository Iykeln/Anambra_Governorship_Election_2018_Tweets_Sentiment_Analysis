## The Impact of Political Party/Candidate on the Election Results From A Sentiment Analysis Perspective Using #AnambraDecides2017 Tweets
####  This ```repo```  contains the experimental resources we used to investigates empirically the impact of political party control over its candidates or vice versa on winning an election using a natural language processing (NLP) technique called sentiment analysis (SA).

The following research questions were evaluated
1. Research Question 1: How sentiment of the tweets for a particular candidate/party behaves across a given time frame to ascertain attitudes of the public towards the political actors?
2. Research Question 2: How subjectivity scores for each candidate/party varied across time and which of the candidate/party whose mention alone got a high frequency score in more subjective tweets?

#### For the paper, see [here](https://link.springer.com/article/10.1007/s13278-020-00667-2) or [here](https://www.researchgate.net/publication/342723934_The_impact_of_political_partycandidate_on_the_election_results_from_a_sentiment_analysis_perspective_using_AnambraDecides2017_tweets)

## Citation
```ruby
@article{onyenwe2020impact,
  title={The impact of political party/candidate on the election results from a sentiment analysis perspective using\# AnambraDecides2017 tweets},
  author={Onyenwe, Ikechukwu and Nwagbo, Samuel and Mbeledogu, Njideka and Onyedinma, Ebele},
  journal={Social Network Analysis and Mining},
  volume={10},
  number={1},
  pages={1--17},
  year={2020},
  publisher={Springer}
}
```
OR

> Onyenwe, I., Nwagbo, S., Mbeledogu, N. et al. The impact of political party/candidate on the election results from a sentiment analysis perspective using #AnambraDecides2017 tweets. Soc. Netw. Anal. Min. 10, 55 (2020). https://doi.org/10.1007/s13278-020-00667-2.

## Repository Content
This repo contains the Twitter dataset (#AnambraDecides2017 Tweets) and the Python codes (notebook IDE).

### Twitter Dataset 
We use the Twitter Streaming API to download tweets related to 3 keywords: ```\#anambradecides2017, \#anambraelections and \#anambradecides``` on the day of the election. The objective of the real-time collection was to collect only tweets about the election published on the same day. We based on the hypothesis that if there is a tweet about Anambra State election that same day, then that tweet could be making a reference to what the user is experiencing at the moment about the election. The dataset can be found [here](https://raw.githubusercontent.com/Iykeln/Anambra_Governorship_Election_2018_Tweets_Sentiment_Analysis/main/dataset/filtered_attributes_stream_Anambra.csv)

## Sample Codes and Results
Exploratory data analysis for names of interest counts. We investigated how the political keyplayers (we are interested in) are mentioned given the collected tweets.

```ruby
names = ['willie_obiano','oseloka_obaze','nwoye_tony','godwin_ezeemo','osita_chidoka']
tweets_by_name = [originals['willie_obiano'].value_counts()[True], 
                  originals['oseloka_obaze'].value_counts()[True], 
                  originals['nwoye_tony'].value_counts()[True], 
                  originals['godwin_ezeemo'].value_counts()[True],
                  originals['osita_chidoka'].value_counts()[True]]
x_pos = list(range(len(names)))
width = 0.8
fig, ax = plt.subplots(figsize=(12, 8))
plt.bar(x_pos, tweets_by_name, width, alpha=1, color='g')
ax.set_ylabel('Number of tweets', fontsize=25, fontweight='bold')
ax.set_title('Counts for names of interest', fontsize=25, fontweight='bold')
ax.set_xticks([p + 0.0 * width for p in x_pos])
ax.set_xticklabels(names,fontsize=17,fontweight='bold',rotation=20)
ax.set_xlabel('Top 5 Candidates',fontsize=25)
plt.grid()
plt.savefig('./computed_images/tweet_by_name_1', format='png') #replace with your filepath
```
Here is a plot from the above code for political cadidates’ names of interest counts.
![alt text](http://url/to/img.png)
