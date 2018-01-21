---
layout: article
title: "An Analysis of NYC Subway Usage"
categories: blog
excerpt: "My first project for Metis - an analysis of NYC subway traffic"
tags: [blog, metis]
image:
  feature: nyc-subway.jpg
  teaser: nyc-subway-teaser.jpg
---

I recently quit my job as the Senior Business Analyst at [Sittercity](https://www.sittercity.com/) to take a full-time, three month data science course with [Metis](https://www.thisismetis.com/). Read more about my experience with Metis here. 

At Metis we hit the ground running and were assigned our first of five projects on the very first day - this post is a summary of that project

___

## Project Problem Statement

This first project imagines that we are contacted by a potential client, WomenTechWomenYes, to solicit our help optimizing their street team work to collect the most emails from NYC commuters entering subway stations around the city. 

*WomenTechWomenYes (WTWY) has an annual gala at the beginning of the summer each year. As we are new and inclusive organization, we try to do double duty with the gala both to fill our event space with individuals passionate about increasing the participation of women in technology, and to concurrently build awareness and reach.*

*To this end we place street teams at entrances to subway stations. The street teams collect email addresses and those who sign up are sent free tickets to our gala.*

*Where we’d like to solicit your engagement is to use MTA subway data, which as I’m sure you know is available freely from the city, to help us optimize the placement of our street teams, such that we can gather the most signatures, ideally from those who will attend the gala and contribute to our cause.*


Clearly the goal of this new organization is to **build awareness**, and they're hoping to achieve that goal by 1) connecting with as many commuters as possible and 2) specifically targeting individuals who are most likely to attend their gala and contribute to their cause. 

>> *... help us optimize the placement of our street teams, such that we can gather the most signatures, ideally from those who will attend the gala and contribute to our cause*

Ideally, we would conduct an analysis of the NYC transit system and surrounding areas that would satisfy both objectives by identifying:

**1) The Most Frequented Stations** - The station locations with the highest number of commuters

**2) At Optimized Times** - The times when these stations are most frequented

**3) In Ideal Areas** - The stations in areas most densely populated with tech companies and households likely to donate to non-profit organizations

___

## Enter... the Triple Constraint

There is a concept in project management that a project's quality is constrained by time, resources and scope:

 <center><figure>
	<img src="http://ptgmedia.pearsoncmg.com/images/intro_9780133839753/elementLinks/01fig01.jpg" alt="">
</figure></center>

Because our time and resources were fixed, (my group had three people, 4 days, and only open source data/tools) we decided to limit the scope of our project to avoid producing low quality results.

In the end, our goal was to accomplish two things:

> **Our goal is to identify:**

> 1) **The Most Frequented Stations** 

> 2) **At Optimized Times**

___

## Data and Methodology

We were able to pull data directly from the MTA website to get weekly counts of turnstile rotations from each subway station and also a file for subway station location data. There were some limitations here:

- The turnstile rotation counts are sampled at irregular intervals (approximately every four hours)
- The turnstile rotation counts will randomly turn over and start counting backwards
- There is no way to directly link turnstiles to station locations

___

## Results

I put together an interactive dashboard, hosted on Tableau Public, to visualize the results of our analysis and enable exploration of optimal locations for specific periods of time during the months our client would be canvassing.

<center><iframe src="https://public.tableau.com/views/MTA-Entry-Traffic-Dash/StationLocationsandTimes?:showVizHome=no&:embed=true" width="1020" height="900" frameborder="0"></iframe></center>
 



<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px;" href="https://unsplash.com/@o_j_cole?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Oliver Cole"><span style="display:inline-block;padding:2px 3px;"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-1px;fill:white;" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M20.8 18.1c0 2.7-2.2 4.8-4.8 4.8s-4.8-2.1-4.8-4.8c0-2.7 2.2-4.8 4.8-4.8 2.7.1 4.8 2.2 4.8 4.8zm11.2-7.4v14.9c0 2.3-1.9 4.3-4.3 4.3h-23.4c-2.4 0-4.3-1.9-4.3-4.3v-15c0-2.3 1.9-4.3 4.3-4.3h3.7l.8-2.3c.4-1.1 1.7-2 2.9-2h8.6c1.2 0 2.5.9 2.9 2l.8 2.4h3.7c2.4 0 4.3 1.9 4.3 4.3zm-8.6 7.5c0-4.1-3.3-7.5-7.5-7.5-4.1 0-7.5 3.4-7.5 7.5s3.3 7.5 7.5 7.5c4.2-.1 7.5-3.4 7.5-7.5z"></path></svg></span><span style="display:inline-block;padding:2px 3px;">Oliver Cole</span></a>