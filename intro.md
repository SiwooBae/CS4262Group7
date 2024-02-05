# Quantifying the Unquantifiable with Natural Language Processing: Finding Similarities between US Companies Based on Their Descriptions 

## Why?
Imagine you want to invest in a house. One day, you find a nice house in a suburb that is currently for sale for 1 million dollars when every neighboring house is traded for 2 million dollars. Given that the house has roughly the same quality as others (and not haunted for sure; you called an exorcist the other day to double check), should you buy this house? The answer is: Yes! The house in question seems to be relatively *undervalued* compared to its *peers*.

We can apply the same logic to the stock market. If a company is priced significantly cheaper than its peers even though it is just as strong and stable as them, one may expect the company is undervalued. In the world of stock investment, this is called [Multiples Analysis](https://www.investopedia.com/terms/m/multiplesapproach.asp) and it is considered one of the most common way to value a company.

But what does it really mean for two companies to be *similar* to each other? Our intuition tells us Apple and Samsung are similar, but we can't really tell exactly how much they are similar to each other. How much similarity should we account for? How significant is the difference? Are these two companies truly "peers" to each other when it comes to Multiples Analysis?

Answers to those questions have been what separated successful fund managers from the unsucessful ones: good investors would have keen insights on how similar they are, while bad investors would fumble for comparing apples to oranges.

We, the data science people, do not really like when things are not quantitative. So, with the power of NLP, let's turn them into numbers. I will show the data science and ML approach to the company similarity problem.


## What is the dataset you chose? (include a link to the dataset)

I chose the [company profile dataset](https://site.financialmodelingprep.com/developer/docs#company-profile-company-information), and historical stock prices dataset fetched from [Yahoo API package](https://pypi.org/project/yfinance/). Since the former is paywalled, and the latter will take hours to get, I aggregated them all and uploaded them as .csv files in Notebook(s) folder.

### What is the focus question you are trying to answer with this dataset? Include whether this is a classification, clustring, or other type of problem.

1. Traditionally, stock peers have been rather naively decided using 1. which sector and industry they are in, 2. some balance sheet numbers like total asset and/or market cap, 3. heuristic "gut instinct." Instead, can we directly measure the similarity between companies by only using their descriptions, without relying on the human "gut instinct"? This should be considered as a **clustering** problem.
2. Furthermore, what other information can we obtain from the descriptions? Can they predict stock returns? Volatility? Can we make a model that takes in your business idea and gives you a ballpark estimate of how much it will succeed? This will be either a **classification** or **regression** problem.

### What is your plan for cleaning this dataset? (you don't have to go into too much detail, just a general idea of what you are going to do)

In order to preserve consistency, I will only use companies that are in the US and traded in the US stock market using sql queries. Then, I will clean out any null values in the data.

### Any extra information you'd like to include

Due to [its nature](https://en.wikipedia.org/wiki/Efficient-market_hypothesis), financial data is one of the hardest yet most fascinating set of data that comes with all sorts of flavors: tables, images, sequences, and languages. It would be a lie if I said making money was never a part of the motivation, but it is not the only motivation, either. As far as I know, there is no other field of study like finance which requires this much of multimodality. It feels like the final boss of all data science problems, which is why I love it.
