---
layout: post
title:  Analysis of text conversations with my wife
excerpt: I was recently going through some of the earliest text conversations between me and my wife. Apart from exposing our naiveness and excitement in a cute way, I found those texts insightful of our personalities and relationship. So I tried to apply what I do for my day job in analyzing the texts data and quantify the conversations.
categories: [Text Analysis, Plotly, WhatsApp Chat processing]
---
I exported the WhatsApp chat for the first two months of our relationship into text file. Since we primarily texted each other on WhatsApp this captures most of our text conversations, but doesn't include phone calls or other media.

After parsing the text file and preprocessing, I looked at the quantity of the messages and the words. It seems like she sent me ~400 more messages than I did, and we overall texted ~4000 messages in two months! However, I sent those "lengthy" texts to makeup for my lesser number of messages as I used 14k words in total comared to 12k of her's.

![png](/images/chat-analysis-fig1.png)

Looks like she does one word texts lot more than me *okay, okies, ohk, vokay, ok, k*, and compensates for the words with higher usage of emojis. **An Emoji is worth 10 words !**

![png](/images/chat-analysis-fig2.png)



I consider myself a curious person and ask lot of questions, taking into account that these messages are from early phase of our relationship its not surprising we ask each other lots of questions. I categorized messages as questions using simple rule based filter, if the message ends with "?" or starts with "why", "what", "where", "who", "when", "how".

![png](/images/chat-analysis-fig3.png)

Apart from the core office working hours or sleeping times, we were pretty reponsive to each other. The response times shown here are in seconds and on an average my wife has faster reponse time compared to me.

A message is considered conversation starter if it sent after a pre defined time window which in this case I set as 6 hours. Finally a criteria where we have almost equal number of stats !=!

![png](/images/chat-analysis-fig4.png)


Next I explored the words used in conversations, I have hidden some words and emojis for privacy reasons. Below you can see our Wordclouds, after removing standard stopwords like 'and', 'or', 'the' etc.

As expected there are plenty of words that characterize the millenial texting habits like "haha", "hahaha", "yup", "soo". It is interesting to see words from three different languages sprinkled all over, as we both are trilingual. My wife had the habit of using these weird short forms for words such as "bcz", "ryt", "ppl", the habit which she shredded off lately :)




![png](/images/chat-analysis-wordcloud1.png)


One thing I like in these commmon words are some hidden inside jokes and ways we used to refer each other #awww




![png](/images/chat-analysis-wordcloud2.png)


This text analysis would be incomplete without looking at the emojis, especially when about 2000 emojis were exchanged in 4300 messages. Clearly each of us have our favourite emojis to respond, though I was bit conservative in throwing emojis. Hey honey, stop winking so much 😉!!

![png](/images/chat-analysis-fig5.png)

Finally, I looked at the number of messages per day and plotted below using Plotly's cool rangeslider. Infact the only reason I examined this metric is it gives me chance for using time series plots of Plotly ;) After loading the messages in Pandas' Series indexed with timestamp, I resampled the data with a time interval of 24 hours for converting un-even spaced time series data to evenly spaced.

Since we had communications outside WhatsApp texts, its hard to make lot of conclusions from this plot. Though I can identify when we had our "sparks", its also striking to see we texted each other everyday !!


![png](/images/chat-analysis-fig6.png)


If you would like to run this analysis on your text conversations, feel free to clone the repository <https://github.com/psrikanthm/WhatChat> and follow the instructions. There are few more stats that are available in the code which I haven't made use of in this analysis.
