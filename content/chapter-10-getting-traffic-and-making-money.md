---
title: "Getting Traffic and Making Money"
chapter: "Chapter 10"
description: "Chapter 10 of the Static Site Guide, a book that explains how to build a static website from scratch."
date: 2025-06-07
previous: 
  name: "Chapter 9"
  link: "/chapter-9-setting-up-continuous-deployment/"
next: 
  name: "Conclusion"
  link: "/conclusion/"
---

Building a static website with a custom domain name, version control, and continuous integration is no small feat. But the reality is that building a website might seem relatively easy compared to what comes next. Driving traffic to your website and monetizing it both require hard work, patience, and ingenuity.

To be clear, you don’t have to worry about this if you don’t care who visits your website. Maybe you intend for family and friends to be the only audience. There’s nothing wrong with that! But most people want to get as many eyeballs as possible on their new website.

In this chapter, you'll learn how to submit your website's sitemap to Google. You'll also learn about search engine optimization (SEO) techniques that can make your web pages appear higher in search results. Finally, you'll learn how to make money from your website.

## Submitting a Sitemap to Google

Google is the world’s largest search engine, but it doesn’t know about your website, at least not yet. There are more websites than there are people alive on the planet, and even with all of Google’s computing resources, it still can’t find every single website without some help. 

You can help Google find your website by submitting a *sitemap*. 

When Hugo builds your website, it automatically creates a `sitemap.xml` file in the `/public` directory. This file contains a list of every web page available on your website. Search engines like Google read the `sitemap.xml` file to find your web pages, and then they crawl your website to index the content.

{{< aside type="tip" >}}
You can view the sitemap file for your website by appending `sitemap.xml` to your domain name. For example, you can view the sitemap for Heroic Tiramisu at <https://heroictiramisu.com/sitemap.xml>. This file is formatted in [XML](https://en.wikipedia.org/wiki/XML) since it’s designed for robots and not human beings.
{{< /aside >}}

Let's make a few small changes before submitting the sitemap to Google. 

### Updating Your Website's config.toml File

Beginning in [Chapter 5](/chapter-5-creating-a-static-website-using-hugo/#configuring-the-theme), we made several modifications to our website's `config.toml` file. Since Hugo uses information in that file to generate the `sitemap.xml` file, we'll need to update the `config.toml` file again to add our website's custom domain. 

Make sure the `baseURL` setting on the first line of `config.toml` contains the URL of your website, as shown below.

```toml {hl_lines=["1"]}
baseURL = "https://heroictiramisu.com/"
languageCode = "en-us"
theme = "terminal"
paginate = 5

[params]
  contentTypeName = "posts"
  themeColor = "turquoise"
  showMenuItems = 1
  fullWidthTheme = false
  centerTheme = true
```

Save the changes to the file, commit the changes to the repository, and push the changes to GitHub. After your website has been deployed, the `sitemap.xml` file will contain the correct URLs.

### Adding and Verifying Your Domain in Google Search Console

There are several ways of submitting your sitemap to Google. My preferred way of doing it involves the Google Search Console. First, you'll need to log in to the [Google Search Console](https://search.google.com/search-console). Add your website's domain as a *property*, as shown below.

![Adding a property in Google Search Console](/images/figures/figure-76.png)

After you've done that, Google will need to verify that you own the domain you're adding to Google Search Console. The verification process usually involves adding a special DNS record. The Google Search Console attempts to automatically help you with this, as shown below. 

![DNS verification in Google Search Console](/images/figures/figure-77.png)

Click **Start verification**. If you're using Cloudflare as your domain registrar, as covered in [Chapter 7](/chapter-7-using-a-custom-domain-name/), your web browser will open the Cloudflare website in a new tab and attempt to create the new DNS record needed for Google's verification process, as shown below.

![Creating the new DNS record for DNS verification in Cloudflare](/images/figures/figure-78.png)

Click **Authorize**. When you switch back to the Google Search Console tab in your web browser, you should see a success message. You've successfully verified that you own the domain.

{{< aside type="tip" >}}In [Chapter 7](/chapter-7-using-a-custom-domain-name/), we used DNS records to point our domain name to Netlify. This DNS record is different and doesn’t change how our website works. It’s just a code that Google uses to establish that you own the domain.
{{< /aside >}}

### Submitting the Sitemap

Now that we've added our domain to Google Search Console, we can submit our website's sitemap. 

From the sidebar, select **Sitemaps** and then enter the URL of your website's sitemap. As previously discussed, you can find the sitemap file for your website by appending `sitemap.xml` to your domain name. For example, the URL for the Heroic Tiramisu sitemap is <https://heroictiramisu.com/sitemap.xml>.

![Submitting our sitemap file in Google Search Console](/images/figures/figure-80.png)

Click **Submit**. Your website's sitemap will be successfully submitted to Google, as shown below.

![Sitemap submission success message in Google Search Console](/images/figures/figure-81.png)

You might be wondering what happens next. Will your website start appearing in the results for search queries on Google's website? Probably not immediately—at least not in my experience. It can take Google weeks to read your sitemap file and index the content on your website. Patience is key!

## A Lesson in Managing Expectations 

Let me share my experience getting traffic to [*The Markdown Guide*](https://www.markdownguide.org). It's the most successful website I've ever built. It received over 5 million visitors in 2023. But it wasn't always like this. For the first few years after I started *The Markdown Guide*, I thought it would flop.

Take a look at the screenshot below. It shows the traffic that *The Markdown Guide* received between June 2017 and March 2019. 

![Visitors to the Markdown Guide from 2017 to 2019](/images/figures/figure-75.png)

After I started the website in January 2017, it barely received any traffic even though I submitted the sitemap to Google and got a couple of websites to link to *The Markdown Guide*. But I was patient. I kept adding and updating existing content, asking other websites to link to mine, and improving the technical SEO elements. 

The hard work and patience paid off. By May 2019, the website was receiving over 3,000 visitors per day. Today, it ranks first for the "markdown" keyword and receives over 15,000 visitors per day on average. If you looked at the traffic between 2019 and today, it would look like a hockey stick.

Just think: If I had thrown in the towel back in 2017 or 2018 when *The Markdown Guide* was receiving hardly any traffic, it never would have realized its full potential.

I’m sharing this because I want you to manage expectations when you’re starting. Getting consistent traffic to your website is an endurance race. Hang in there!

## Crash Course in Search Engine Optimization

Because getting traffic to a website can make or break a business, an entire cottage industry around SEO has popped up to help website owners get more traffic on their websites.

SEO is a big topic that I can't adequately cover in a single chapter. But the general idea behind SEO is that you can make minor changes to your website and your website's content so that Google ranks your website higher in search results. 

Imagine that you own a website related to baking. You use an SEO tool to discover that most people searching for cookies use the search term "how to bake chocolate chip cookies." You could use that information to create a new blog post entitled *How to bake chocolate chip cookies*. If that blog post becomes a hit, it could help your baking website rank higher in search results for certain keywords and search phrases, resulting in more people visiting your website.

But beware. Some SEO "advice" consists of gimmicks and snake oil. People peddling these so-called tips have [swampland in Florida they'd like to sell you](https://en.wikipedia.org/wiki/Swampland_in_Florida).

{{< aside type="tip" >}}
[Backlinko](https://backlinko.com/) is the best SEO resource when you're getting started. It's free! My advice is to read as much as you can and try to implement the tips as you read through the guides.
{{< /aside >}}

### Creating Great Content

The cornerstone of any good SEO strategy should also be the most obvious: Your website needs great content that helps human readers.

The internet is drowning in content. At a time when writing blog posts can be outsourced to non-native English speakers or ChatGPT for pennies on the dollar, you need outstanding content that helps set your website apart from virtually every other website on the internet.

My advice is to *compete on quality*. Content has become a commodity, but people will always crave quality content that helps them solve their problems and improve their lives. Create the type of content you wish you had when you started learning about a topic.

When I started *The Markdown Guide*, Markdown had been around for fifteen years. People assumed that Markdown documentation was a solved problem, but it wasn't. I knew from personal experience that the existing Markdown documentation was severely lacking. There were so many mediocre blog posts about how to write using Markdown, but to my knowledge, no one had ever created an entire website for Markdown documentation. 

My hunch was that people were having the same problems I had and that *The Markdown Guide* could solve those problems. Sometimes a hunch like that is all you need.  You can see a gap between the content currently available on the internet and the content you know you can create.

By the way, I’ve been talking about written content, but you could apply these principles to any content—things like artwork, photography, podcasts, and videos.

{{< aside type="tip" >}}
One of my favorite books on this topic is [*Content Inc.*](https://www.amazon.com/Content-Inc-Second-Content-First-Successful-ebook/dp/B08NTWNQFQ) I can't recommend it enough!
{{< /aside >}}

### Getting Links

Having great content on your website is a good start, but it isn't enough to guarantee a high position in search results. That's because Google can't automatically tell which websites have good content. Instead, Google uses the number of inbound links as a signal. In other words, the more links Google finds to your website from other reputable websites, the higher Google will rank your site.

How do you get other websites to link to your website? When you're just starting, you have to ask people. If you followed my advice and created great content, you shouldn't have trouble getting people to link to your website. I've found that most people are eager to share great content with their readers.

Start by looking for websites similar to yours. These could be blogs, news websites, or even communities on Reddit. Then find a way to contact the website's owner. Usually, you can find an email address or contact form. Explain that you've started a new website, and that you think their readers would appreciate some of your content. Would they mind adding a link to your website?

For the first link to *The Markdown Guide*, I emailed the owner of [Dillinger.io](https://dillinger.io/), an online Markdown editor. I noticed that Dillinger was ranking high for the "markdown" search term and had a "Cheat Sheet" link to a blog post about how to use Markdown. I suggested using my website instead:

> Hi Joe,
>
> I apologize for emailing you at your work email address. I didn't know
how else to contact you besides opening a pull request, and that seemed
like a bad idea without talking to you first.
>
> I've been working on a free and open source Markdown guide for the past
couple months, and I wondered if you might be open to linking to it from
within Dillinger. Here's the link to the guide:
>
> https://www.markdownguide.org
>
> I think it might be a good drop-in replacement for the "Cheat Sheet"
link in the Dillinger menu. Let me know if this is something you're
interested in -- I'd be happy to open a pull request.
>
> Thanks,  
> Matt

He wrote back the next day and said "Please open a pull request." Since Dillinger is an open-source project, I did, and just like that—boom! My website was linked to by Dillinger.io. 

You can use the same principles to ask for links to your website. When you start getting links to your website from other websites, Google will gradually start moving your website up in search results. 

### Using SEO Tools

Sometimes, no matter how much reading and research you do, you need someone or something to analyze your website and offer advice. That's where automated SEO tools come in. A good SEO tool will scan your website and tell you how to fix the SEO issues it identifies.

My favorite SEO tools are [Ahrefs](https://ahrefs.com/), [Moz](https://www.moz.com), and [Semrush](https://www.semrush.com/)—pick one. Ahrefs is arguably the best for solo developers—its dashboard is shown below.

![The Ahrefs dashboard](/images/figures/figure-82.png)

These tools aren't cheap. Subscriptions start at $99 per month and go up from there. But if you're serious about improving your website's SEO, you'll want to use one of these tools for a few months.

All of these tools automatically scan your website for problems. Some problems will be deemed critical errors, and you should fix those as soon as possible. Most issues will be non-critical—you can fix them at your leisure. Creating new content and getting links to your website is probably more important than fixing non-critical issues.

The tools are helpful in other ways, too. They keep track of the number of backlinks to your website and how your web pages rank for various search terms. You can review your progress over time to make sure you're improving. The idea is that, as you fix issues, add content, and obtain new backlinks to your website, your domain rating will increase over time, and your search rankings will improve as a result.

## Tracking Visitors

One of the most exciting aspects of owning a website, for me at least, is seeing how many people have visited it. This isn't a requirement—you don't *need* to know how many people have visited your website. If you decide this is something you want to do, you'll need to decide on a third-party tool and then add a bit of code to your website's template.

There are lots of tools that you can use to track visitors to your website. One of the most popular options is [Google Analytics](https://analytics.google.com). I've used Google Analytics in the past, but now I prefer using privacy-focused solutions like [Plausible](https://plausible.io/) and [Simple Analytics](https://www.simpleanalytics.com/). 

Plausible is the stand-out option since it's [open source](https://github.com/plausible/analytics) and can be self-hosted on your server. (They also have a hosted option.) It's what I use for my websites. You can see the real-time dashboard below.

![The Plausible dashboard](/images/figures/figure-83.png)

After you subscribe to Plausible or get it set up on your server, you can add a line to your website's `baseof.html` layout file, before the `</head>` tag:

```html
<script defer data-domain="heroictiramisu.com" src="https://plausible.io/js/plausible.js"></script>
```

It’s fun to set this up and watch people visit in real time, but remember what we discussed earlier. Getting consistent traffic to your website is an endurance race. Don't get discouraged if your website doesn't get lots of traffic at first.

## Making Money From Your Website

Some people create websites out of the goodness of their hearts and don't expect anything in return. Others hope to generate enough money to pay themselves for the time they put into creating the content. One thing is for certain: Monetizing a website is hard work, and making money isn't guaranteed no matter how much time and effort you put into a website.

That said, if you want to try making money from your website, there are two primary ways of doing it. You can display advertising on your web pages, or you can sell products to readers.

### Displaying Advertising

Advertising is a tried-and-true way to make money from your website. These days, most people put code into their website's template to display the advertising, and a third party handles virtually everything from procurement, display, and analytics to payment. 

[Google AdSense](https://adsense.google.com/start/) might be the best option for display advertising. You sign up, add the code to your website, and start earning money. It's that simple. Google can automatically tell which type of ads fit the content on your website.

Of course, Google AdSense is only one option. There are plenty of other advertising networks out there. For example, if your website's content focuses on technology, you could apply to join [EthicalAds](https://www.ethicalads.io/publishers/), [Carbon](https://www.carbonads.net/), or [BuySellAds](https://www.buysellads.com/publishers).

Another option is selling advertising space yourself. John Gruber does that on [Daring Fireball](https://daringfireball.net/feeds/sponsors/)—he makes tens of thousands of dollars a month that way!

### Selling Products

Using your website as a funnel to sell products is another viable money-making option. 

For example, I packaged *The Markdown Guide's* content into an ebook and started selling it on [Gumroad](https://gumroad.com/about) and Amazon for $5. I wasn't sure what to expect when I did that. Would people pay for an ebook that's free to read online? It turns out they do. Since I launched the book for sale in 2020, I've sold thousands of copies.

Repackaging and selling your website’s content is an obvious option. But there are plenty of other products you could experiment with making. For example, you could create video training courses, t-shirts, stickers, teacher lesson plan templates, fonts, or Excel spreadsheet templates. Use your imagination—you might be surprised what people will pay for.

In many ways, selling products directly to your website's visitors is preferable to using marketplaces like Amazon or Etsy. Cut out the intermediaries, and you'll retain more of the earnings from sales. There are third-party services that can help you sell products. [Gumroad](https://gumroad.com/about) and [Payhip](https://payhip.com) are "no-code" solutions that handle payments and taxes. Or, if you want to create a seamless experience, [Stripe Checkout](https://stripe.com/payments/checkout) and [Stripe Payment Links](https://stripe.com/payments/payment-links) are great options.

{{< aside type="tip" >}}
If you're interested in creating and selling products, I recommend checking out [Indie Hackers](https://www.indiehackers.com/) and [Small Bets](https://smallbets.com/). These communities provide a variety of classes, workshops, and interviews with successful founders. There's a lot of helpful advice for people willing to experiment.
{{< /aside >}}

## Next Steps

Driving traffic to your website and monetizing that traffic is a process that takes time. In many ways, the work never stops. Keep creating new content, improving existing content, and asking other websites to link to your website. 

You may not see immediate results, but stick with it. This work is an investment that will pay dividends over time. With hard work and a little luck, you'll see traffic to your website slowly increase.