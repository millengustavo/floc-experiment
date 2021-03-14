# Federated Learning of Cohorts (FLoC) - Google's solution for interest based advertising in a world without third-party cookies

![cookies](food-photographer-jennifer-pallian-OfdDiqx8Cz8-unsplash.jpg)

Photo by <a href="https://unsplash.com/@foodess?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Food Photographer | Jennifer Pallian</a> on <a href="/s/photos/cookie?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>

## The end of third-party cookies for advertisers

Third-party cookies have (since 1994) been a key enabler of the commercial Internet and **fine-grained digital ad targeting**

They helped achieve **unprecedented audience segmentation and attribution** - helping to connect marketing tactics with results in ways that were virtually impossible in the most traditional forms of media.

To bring users more transparency and better consent management, most browsers are ending support for third-party cookies.

- [Firefox 79 clears redirect tracking cookies every 24 hours](https://venturebeat.com/2020/08/04/mozilla-firefox-79/)
- [Apple teases new tracking protections and an approximate location feature in iOS 14](https://www.theverge.com/2020/6/22/21299407/apple-ios-14-new-privacy-features-data-location-tracking-premissions-wwdc-2020)
- [Google has announced plans to stop supporting third-party cookies on its Chrome browser in 2021](https://blog.chromium.org/2020/01/building-more-private-web-path-towards.html)

Some alternatives are being proposed to replace the need for third-party cookies, ensuring users' privacy, but without loss of performance for advertisers.

In this post you will learn a little more about **FLoC**, an alternative proposed by Google, and we will navigate through a simplified demonstration of the algorithm using a public dataset.

## FLoC's Goal
> **"Preserve interest based advertising, but in a privacy-preserving manner"**

### Overview
- Relies on a **cohort** assigning mechanism: a function that allocates a cohort id to a user based on their **browsing history**
- This cohort id **must be shared by at least k distinct users** for privacy

### Privacy x Utility
> "The more users share a cohort id, the **harder it is to derive individual** user's behavior from across the web. On the other hand, a large cohort is more likely to have a diverse set of users, thus making it harder to use this information for **fine-grained ads personalization** purposes."

**Ideal cohort assignment**: group together a large number of users interested in similar things

### Intersections with Data Science
- [Federated Learning](https://federated.withgoogle.com/): machine learning technique that trains an algorithm across multiple decentralized edge devices or servers holding local data samples, **without exchanging them**
- Cohort assignment algorithm should be **unsupervised**, since each provider has their own optimization function

## Full experiment
[Open jupyter notebook](floc_movielens.ipynb)
