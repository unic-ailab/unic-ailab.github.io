

<p><span style="font-size: 32px;"><b>Public Sentiment and Stances on AI: Insights from Comments on Recent Developments</b></span><br>
<br>

<span style="font-size: 20px;">Reading that this helpful new gadget, called ChatGPT, that just yesterday wrote an entire essay for your homework, might become as threatening as a nuclear war can be both unsettling and peculiar. Recently, industry leaders involved in AI development warned the public of how dangerous the unregulated development of AI systems can turn out to be. Artificial Intelligence systems are still a brave new frontier with most communities still uncertain of their limits and capabilities. Nonetheless, foreboding news easily turn into a magnet for internet denizens to flock around and voice their opinion.<br>
<br>
One such avenue was the corresponding <a href="https://www.nytimes.com/2023/05/30/technology/ai-threat-warning.html">article</a> by the New York Times, informing the public of the unnerving one-sentence statement signed by more than 350 individuals actively involved in AI research and commercialization. More than 1400 comments were promptly posted under the article. As the advent of the next level of AI systems was sudden in recent years, the average view is still not firmly established. A lack of consensus appears to be the main take-away after a few glances in the first few comments, not very much unlike how <a href="https://www.washingtonpost.com/technology/2023/05/20/ai-existential-risk-debate/">experts are recently divided</a>. As such, it was of interest to try and analyze the public’s tendencies around the matter.<br>
</span><br><br>


<span style="font-size: 26px;"><b>Sentiment Analysis</b></span><br>
<br>
<span style="font-size: 20px;">In sentiment analysis, sentiment refers to the underlying emotion expressed in a piece of text. Through the analysis we aim to determine whether a given text expresses a positive, negative, or neutral sentiment, with the ultimate goal of reaching insights regarding public opinion. The process often uses various techniques varying from looking for specific keywords, to linguistic patterns or contextual information. Presently, however, the <a href="https://www.sciencedirect.com/science/article/pii/S2468696422000039">model</a> we deployed relies on neural network architecture in order to learn from documents and classify sentiment.<br><br>
Our first step was to gauge the public sentiment based on the comments. The model used,  developed here in UNIC’s <a href="https://ailab.unic.ac.cy/">AI Lab</a>, is the perfect candidate for that task. The model is capable of reading textual documents and deciphering whether the sentiment hidden behind the words is positive, negative or neutral. We deployed the model on the comments and one can say the results are surely intriguing. As you can see in the following figure the public appears to be mostly split between positive and negative sentiments regarding the article’s content. While some are happy about what they read, others view the news in a negative light.<br><br>

<img src="assets/imgs/posts sent.png"><br><br>

The comments section of an article is often the ground of heated discussions between users. Based on the sentiment the comments echoed, we analyzed the number of replies they received within the first couple of days that the article went live. We can see how the, expectedly, increased activity of the first hour was strongly polarized. The figure is fully interactive, and one can use the slider to zoom in and out in the time domain, or choose the particular sentiment they wish to display, by clicking on it from the legend. <br><br>
<iframe src="assets/html/sentiment_time_series.html" width="100%" height="500px"></iframe><br><br>
<span style="font-size: 26px;"><b>Topic Modeling</b></span><br><br>
An interesting first insight, although what would be even more interesting is finding the discussions those comments revolve around. A great way to achieve this, bar reading 1500 comments, is topic modeling. Topic modeling allows us to cluster the discussion under different categories based on their content. The algorithm we followed yielded five distinct topics. The comments were then assigned to their respective topic and the connections to their replies were established. In the following interactive map one can explore the various comments, how they are connected and what topic they belong to. Zooming into the map allows for better visualizing the connections between the comments. <br><br>
<iframe src="assets/html/graph_coms_topics.html" width="100%" height="850px"></iframe><br><br>



Still, there was a feeling that we can learn more about those topics. We ended up diving deeper into what’s hidden in those clusters and uncover the most influential words that made the topics what they are.<br><br></span>


<style>
    .container {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }
    .topic {
        text-align: center;
        margin: 10px;
    }
    .image {
        margin: 10px;
    }

</style>
<body>
    <div class="container">
        <div class="topic">
            <b>Topic 1: Humanity</b><br>
            <img src="assets/imgs/topic1.png" class="image">
        </div>
        <div class="topic">
            <b>Topic 2: Corporations</b><br>
            <img src="assets/imgs/topic2.png" class="image">
        </div>
    </div>
    <div class="container">
        <div class="topic">
            <b>Topic 3: People vs. Technology</b><br>
            <img src="assets/imgs/topic3.png" class="image">
        </div>
    </div>
    <div class="container">
        <div class="topic">
            <b>Topic 4: Science</b><br>
            <img src="assets/imgs/topic4.png" class="image">
        </div>
        <div class="topic">
            <b>Topic 5: Artificial Intelligence</b><br> 
            <img src="assets/imgs/topic5.png" class="image">
        </div>
    </div>
</body>




<br> <span style="font-size: 26px;"><b>Stance Detection</b></span><br>
<br>
<span style="font-size: 20px;">In order to better understand not only the significance of these words but also the overarching feelings that encompass these five, very distinct, topics we needed to find a way to reveal the commenter’s stance towards the topic at hand through their comments. To achieve this we trained a model to perform Stance Detection on these comments in order to classify them as comments that either support the notion that “AI is a Threat to Humanity”, “AI will benefit Humanity” or remain Ambivalent on the matter. But how exactly does Stance Detection work and how does it differ from the Sentiment Detection mentioned above? While Sentiment Analysis scans the text to discover the Sentiment or, in other words, the emotional charge that permeates the sentences, Stance Detection, on the other hand, works by analyzing the text to decide which Stance or side it takes in a given argument. The results, given the overall tone and subject matter of the article, were not shocking at all with the vast majority of the comments supporting the notion that AI is a Threat to humanity as a whole.<br><br>

<iframe src="assets/html/pie_stance.html" width="100%" height="600px"></iframe>

This was also a good opportunity to see the rate at which the comments belonging to each Stance were posted over the course of the first 24 hours. <br><br>

<iframe src="assets/html/comments_per_stance_per_hour.html" width="100%" height="500px"></iframe><br><br>
We can see that the first couple of hours was when the bulk of the comments, and especially the ones conveying the idea that AI is a Threat, were posted. We checked to see if the Article was posted anywhere with high traffic during that critical window but nothing of significance was identified. <br>
Could it be that everyone really is against AI or is it a case of people who have already adopted an Anti-AI narrative being drawn to an article that depicts AI in a relatively negative light? Whatever the case may be, we were sure that the data contained more insights yet to be uncovered which is exactly why we decided to perform even more analytical procedures in order to extract as much information as possible. Before performing an even deeper dive into the data, though, we figured this was a good opportunity to supplement our previous understanding of the words that were used by taking a look at the top most frequently used words, regardless of the topic, and how they stack up for each respective stance.<br><br>
<iframe src="assets/html/words_per_stance.html" width="100%" height="600px"></iframe><br><br></span>

<span style="font-size: 26px;"><b>Sarcasm Detection</b></span><br>
<br>
<span style="font-size: 20px;">After taking a closer look at the comments and weighing them against their classified Stances and Sentiments we couldn’t help but notice that quite a few of them made ample use of sarcasm with comments being either fully ironic or having an ironic remark or two hidden somewhere in the almost paragraph-esque combination of sentences that made them up. So, in similar fashion to the Stance Detection we trained another model that this time detects instances of Sarcasm in the comments and classifies them as either containing Sarcasm or not. Again, the results were not very surprising with most Sarcastic or Sarcastically-leaning comments being Anti-AI. This could also provide an explanation for most, if not all, of the instances of Anti-AI comments that are Positive in their Sentiment.<br><br></span>



<iframe src="assets/html/heatmap_stance_sentiment.html" width="100%" height="600px"></iframe>
<iframe src="assets/html/heatmap_stance_sarcasm.html" width="100%" height="600px"></iframe>
<iframe src="assets/html/stacked_stance_sentiment.html" width="100%" height="600px"></iframe>
<iframe src="assets/html/stacked_stance_sarcasm.html" width="100%" height="900px"></iframe><br><br>



<span style="font-size: 26px;"><b>Effort and Interactions</b></span> <br>
<br>
<span style="font-size: 20px;">But, what about the overall effort that has been put into these comments? Surely, not everyone has the time or the way with words to “pen” down eloquent strings of words that carry across the meaning of what they’re thinking. Luckily for us, there is a way to gain an insight into this as well by examining the amount of words that each comment has and grouping them together into meaningful groups per their size or “bins” as they’re more commonly called.<br><br>
<iframe src="assets/html/hist_comment_char_length.html" width="100%" height="600px"></iframe><br><br>
This reveals that the vast majority of comments is on the shorter side with only a tiny minority breaching the 1,000 character threshold. But what exactly does this tell us? <a href="https://elifesciences.org/articles/18422">Research</a> has shown that humans, when presented with multiple choices, are more likely to choose to perform the action that seems the easiest and requires the least effort. Therefore, the analysis above seems to be in line with that observation but, are comments with only a few characters really the option that requires the least effort? While having the least amount of characters can definitely indicate the overall effort that has been put into a comment it turns out that there’s an even easier action that readers can take - one that requires no typing at all; liking the already-posted comments they agree with. As liking a comment you agree with is quicker and easier than typing out a comment that, if anything, serves only as a paraphrasing of what has already been said, it was no surprise to see that all the comments we analyzed have collectively gathered a whopping 23,042 likes. Therefore adding likes into the equation allows us to gain an additional perspective into the Stances displayed in the data. <br><br>
<iframe src="assets/html/heatmap_likes_over_stance_sentiment.html" width="100%" height="600px"></iframe><br><br>

Based on the above we can infer that the comments that generated the most “buzz” and echoed the loudest amongst the readers of this article were the ones with the “AI is a Threat” stance across all sentiments with the comments with a Neutral Sentiment and the Stance that “AI is Not a Threat” following right behind (could it be a case of reserved/grounded optimism?). Lastly, we decided to visualize the overall interactions that the comments received while taking into account their effort (character length) and their Topic. To achieve that we created a Scatterplot where all the points are distributed in the space based on their Likes and Character Length and where each point’s Size and Colour dictate the number of Replies they received and which Topic they belong to respectively.<br></span><br>

<iframe src="assets/html/scatter.html" width="100%" height="500px"></iframe><br><br>

<span style="font-size: 26px;"><b>Conclusion and Results</b></span><br>
<br>
<span style="font-size: 20px;">Overall, we see that the most interacted with comments dealt with the subjects of Humanity and Humanity vs AI/Machines and judging by our prior Analysis of Stance and Sentiment it appears that the majority of commenters don’t seem to share the brightest outlook on the immediate future of humanity in a post-AI-boom world. So, after all this you might be wondering, “What does an average comment from that article look like?”. Well, we have an answer for that as well! While we can’t necessarily share with you the comments as they are, due to privacy-related concerns, we thought it would be interesting to “feed” these comments into an LLM, GPT-4 to be precise, and ask it to return comments that resemble the ones we gave it. The results are actually surprisingly accurate with comments such as:<br>
<br>
1. "AI is a double-edged sword, and we need to be careful how we wield it."<br>
2. "We need to be aware of the potential consequences of AI and take steps to ensure it is used responsibly."<br>
3. "The potential for AI to be used for nefarious purposes is real, and we must be vigilant in our efforts to prevent it."<br>
4. "The power of AI should not be underestimated, and we must be prepared to face the consequences of its misuse."<br>
<br>
Since we have spent quite some time with the actual comments we can confirm that these are really close to the real deal and contain most, if not all, of the concerns that the “AI is a Threat” demographic seems to share. Of course there were also comments that believed that AI will not only help Humanity in the short term by improving the current quality of life (e.g Automation in Medicine) but will also be the foundation of our future but as these comments were few and far between it is only logical that the model returned only the first type of comment as the average.<br></span>
