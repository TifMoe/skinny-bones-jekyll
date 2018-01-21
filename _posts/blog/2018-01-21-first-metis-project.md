---
layout: article
title: "An Analysis of NYC Subway Usuage"
categories: blog
excerpt: "My first project for Metis - an analysis of NYC subway traffic"
tags: [blog, metis]
image:
  feature: nyc-subway.jpg
  teaser: nyc-subway-teaser.jpg
---

I recently quit my job as the Senior Business Analyst at [Sittercity](https://www.sittercity.com/) to take a full-time, three month data science course with [Metis](https://www.thisismetis.com/). Read more about my experience with Metis here. 

At Metis we hit the ground running and were assigned our first of five projects on the very first day - this post is a summary of that project

## Project Problem Statement

This first project imagines that we are contacted by a potential client, WomenTechWomenYes, to solicit our help optimizing their street team work to collect the most emails from NYC commuters entering subway stations around the city. 

*WomenTechWomenYes (WTWY) has an annual gala at the beginning of the summer each year. As we are new and inclusive organization, we try to do double duty with the gala both to fill our event space with individuals passionate about increasing the participation of women in technology, and to concurrently build awareness and reach.*

*To this end we place street teams at entrances to subway stations. The street teams collect email addresses and those who sign up are sent free tickets to our gala.*

*Where we’d like to solicit your engagement is to use MTA subway data, which as I’m sure you know is available freely from the city, to help us optimize the placement of our street teams, such that we can gather the most signatures, ideally from those who will attend the gala and contribute to our cause.*


Clearly the goal of this organization is to **build awareness**, and they're hoping to achieve that goal by 1) connecting with as many commuters as possible and 2) specifically targeting individuals who are most likely to attend their gala and contribute to their cause. 

Ideally, we would conduct an analysis of the NYC transit system and surrounding areas that would satisfy both objectives by identifying:

 - **The Most Frequented Stations** - The station locations with the most frequent commuters entering
 - **At Optimized Times** - The times when these stations are most frequented
 - **In Ideal Areas** - The stations in areas most densely populated with tech companies and households likely to donate to non-profit organizations

## Enter the Triple Constraint

There's a concept in project management that every project's quality is constrained by time, resources and 

 <figure>
	<img src="http://ptgmedia.pearsoncmg.com/images/intro_9780133839753/elementLinks/01fig01.jpg" alt="">
</figure>

Given we were super constrained on time and had fixed resources (a team of three people, with limited bandwidth, using open source data/tools) we decided to limit the scope of our project to product high quality results

In the end, our goal was to accomplish two things:

> 1) Identify the NYC stations that have the highest frequency of commuters

> 2) Identify the times of day these stations are most frequented


## Data and Methodology

We were able to pull data directly from the MTA website to get weekly counts of turnstile rotations from each subway station and also a file for subway station location data. There were some limitations/assumptions here:

- The turnstile rotation counts are sampled at irregular intervals (approximately ever four hours)
- The turnstile rotation counts will randomly

Incididunt umami sriracha, ethical fugiat VHS ex assumenda yr irure direct trade. Marfa Truffaut bicycle rights, kitsch placeat Etsy kogi asymmetrical. Beard locavore flexitarian, kitsch photo booth hoodie plaid ethical readymade leggings yr.

Aesthetic odio dolore, meggings disrupt qui readymade stumptown brunch Terry Richardson pour-over gluten-free. Banksy american apparel in selfies, biodiesel flexitarian organic meh wolf quinoa gentrify banjo kogi. Readymade tofu ex, scenester dolor umami fingerstache occaecat fashion axe Carles jean shorts minim. Keffiyeh fashion axe nisi Godard mlkshk dolore. Lomo you probably haven't heard of them eu non, Odd Future Truffaut pug keytar meggings McSweeney's Pinterest cred. Etsy literally aute esse, eu bicycle rights qui meggings fanny pack. Gentrify leggings pug flannel duis.

## Forage occaecat cardigan qui

Fashion axe hella gastropub lo-fi kogi 90's aliquip +1 veniam delectus tousled. Cred sriracha locavore gastropub kale chips, iPhone mollit sartorial. Anim dolore 8-bit, pork belly dolor photo booth aute flannel small batch. Dolor disrupt ennui, tattooed whatever salvia Banksy sartorial roof party selfies raw denim sint meh pour-over. Ennui eu cardigan sint, gentrify iPhone cornhole. 

> Whatever velit occaecat quis deserunt gastropub, leggings elit tousled roof party 3 wolf moon kogi pug blue bottle ea. Fashion axe shabby chic Austin quinoa pickled laborum bitters next level, disrupt deep v accusamus non fingerstache.

Tote bag asymmetrical elit sunt. Occaecat authentic Marfa, hella McSweeney's next level irure veniam master cleanse. Sed hoodie letterpress artisan wolf leggings, 3 wolf moon commodo ullamco. Anim occupy ea labore Terry Richardson. Tofu ex master cleanse in whatever pitchfork banh mi, occupy fugiat fanny pack Austin authentic. Magna fugiat 3 wolf moon, labore McSweeney's sustainable vero consectetur. Gluten-free disrupt enim, aesthetic fugiat jean shorts trust fund keffiyeh magna try-hard.

## Hoodie Duis

Actually salvia consectetur, hoodie duis lomo YOLO sunt sriracha. Aute pop-up brunch farm-to-table odio, salvia irure occaecat. Sriracha small batch literally skateboard. Echo Park nihil hoodie, aliquip forage artisan laboris. Trust fund reprehenderit nulla locavore. Stumptown raw denim kitsch, keffiyeh nulla twee dreamcatcher fanny pack ullamco 90's pop-up est culpa farm-to-table. Selfies 8-bit do pug odio.

### Thundercats Ho!

Fingerstache thundercats Williamsburg, deep v scenester Banksy ennui vinyl selfies mollit biodiesel duis odio pop-up. Banksy 3 wolf moon try-hard, sapiente enim stumptown deep v ad letterpress. Squid beard brunch, exercitation raw denim yr sint direct trade. Raw denim narwhal id, flannel DIY McSweeney's seitan. Letterpress artisan bespoke accusamus, meggings laboris consequat Truffaut qui in seitan. Sustainable cornhole Schlitz, twee Cosby sweater banh mi deep v forage letterpress flannel whatever keffiyeh. Sartorial cred irure, semiotics ethical sed blue bottle nihil letterpress.

Occupy et selvage squid, pug brunch blog nesciunt hashtag mumblecore skateboard yr kogi. Ugh small batch swag four loko. Fap post-ironic qui tote bag farm-to-table american apparel scenester keffiyeh vero, swag non pour-over gentrify authentic pitchfork. Schlitz scenester lo-fi voluptate, tote bag irony bicycle rights pariatur vero Vice freegan wayfarers exercitation nisi shoreditch. Chambray tofu vero sed. Street art swag literally leggings, Cosby sweater mixtape PBR lomo Banksy non in pitchfork ennui McSweeney's selfies. Odd Future Banksy non authentic.

Aliquip enim artisan dolor post-ironic. Pug tote bag Marfa, deserunt pour-over Portland wolf eu odio intelligentsia american apparel ugh ea. Sunt viral et, 3 wolf moon gastropub pug id. Id fashion axe est typewriter, mlkshk Portland art party aute brunch. Sint pork belly Cosby sweater, deep v mumblecore kitsch american apparel. Try-hard direct trade tumblr sint skateboard. Adipisicing bitters excepteur biodiesel, pickled gastropub aute veniam.

<a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px;" href="https://unsplash.com/@o_j_cole?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Oliver Cole"><span style="display:inline-block;padding:2px 3px;"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-1px;fill:white;" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M20.8 18.1c0 2.7-2.2 4.8-4.8 4.8s-4.8-2.1-4.8-4.8c0-2.7 2.2-4.8 4.8-4.8 2.7.1 4.8 2.2 4.8 4.8zm11.2-7.4v14.9c0 2.3-1.9 4.3-4.3 4.3h-23.4c-2.4 0-4.3-1.9-4.3-4.3v-15c0-2.3 1.9-4.3 4.3-4.3h3.7l.8-2.3c.4-1.1 1.7-2 2.9-2h8.6c1.2 0 2.5.9 2.9 2l.8 2.4h3.7c2.4 0 4.3 1.9 4.3 4.3zm-8.6 7.5c0-4.1-3.3-7.5-7.5-7.5-4.1 0-7.5 3.4-7.5 7.5s3.3 7.5 7.5 7.5c4.2-.1 7.5-3.4 7.5-7.5z"></path></svg></span><span style="display:inline-block;padding:2px 3px;">Oliver Cole</span></a>