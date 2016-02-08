---
layout: post
title:  "My Website: Faults and All"
date:   2016-02-10 13:54:10
categories: journal development ux
---
A review of prototype Version 1.1 of benjaminkinzer.com

This site was a further exploration into Prototyping within the web browser and skipping the various Photoshop files or Sketch boards. I love code and with Jekyll and SASS I can generate a fully functional front-end without spending countless hours managing multiple files. This method also provides me with room to experiment and test quickly how responsive the site actually is.

The goal was also to share my insights and maintain a history of my process and to eventually build out an archive of all my work that would function something like a Novel written by Mark Z. Danielewski that includes a CLIFF NOTES version for the people who only like staring at pictures.

Unfortunately I've been so busy this has been more like Slack Prototyping.

## The Problem
Currently the site is a **user experience** nightmare for my audience and for myself as far as updating is concerned. So let's dive in.

- - -

## Home

![Benjamin Kinzer Homepage]({{ base.url }}/images/benjaminkinzer/v1-1/bk-home.jpg)

For me the home page works well, it's not ideal. But the feedback I have received is positive. The user has a few jumping points, but the work is there before them to interact with. I think in the future it will be worth considering a redesign, but for now it works.

### For Consideration
- Journal Entries on Home

- - -

## Projects

This page does not exist, so people must click on BENJAMIN KINZER to reach the project thumbnails. This has caused a lot of confusion in navigating between projects. The user also must scroll to the top or use the back button to reach other projects.

### For Consideration
- Add **Projects** to navigation
- ADD MORE WORK!

- - -

## Project Detail

![Benjamin Kinzer Project Detail]({{ base.url }}/images/benjaminkinzer/v1-1/bk-project-detail.jpg)

Project detail from a design perspective is alright and it works well on all screen sizes. However, from my stand point this page is a pain in the ass. All the images are background images contained in DIVs. This was so that I could deal with the Art Direction of all the images on various screen sizes.

{% highlight scss %}
$project-folder:  '21stamendment';
$client:          '21a';

%grid {
  @include col(1/1);
  height:205px;
  @include min-screen(nth($res-collection, 2)*1px) {
    @include col(1/2, $cycle: 2);
    height:325px;
  }
}
.hell-high-watermelon {
  @extend %grid;
  @include background-image("#{$project-folder}/#{$client}-mainline-hellorhigh.png");
  background-position:center;
  background-size:118%;
  @include min-screen(nth($res-collection, 2)*1px) {
    background-size:auto;
  }
}
{% endhighlight %}


At the time it was a great idea, but it also required a lot of fussing with background image sizes and managing a stylesheet for each project. I've decided to move away from this method and begin implementing <picture> to control the art direction of each image. At least I will be prepared for future releases from Safari, Firefox and whatever Microsoft is working on.

As for the user, well there is a lot of confusion and extra work to navigate between projects. The user probably feels like they were brought back into the stone ages.

**Let's consider a few scenarios**

- A **User** lands on the home page and clicks on a Project Thumbnail. They're like cool this is fun and scroll down. They now have the option to either use the browser back button or scroll to the top of the page can

Apparently all my project pages have a 100% bounce rate. Should I laugh or cry? If I were viewing my site I would be frustrated that I had to click the back button or scroll to the top to see click on BENJAMIN KINZER to view other work. What if they landed on a specific project page, that rules out the browser back button.

#### For Consideration
- Previous and Next Project Arrows with Thumbnails
- Possibly having related projects in the footer
- Some kind of menu that allows them to jump to other projects within the site

- - -

## Profile

![Benjamin Kinzer Profile]({{ base.url }}/images/benjaminkinzer/v1-1/bk-profile.jpg)

So this page from a user stand point causes a lot of confusion. I've actually used the copy on the page in conversation and it often leads to blank stares. Not sure that is helping me out very much.

#### For Consideration
- Write something that actually makes sense to the reader
- Develop a more friendly concept that conveys the BK story

- - -

## Love

![Benjamin Kinzer Love]({{ base.url }}/images/benjaminkinzer/v1-1/bk-love.jpg)

This page is one of my favorites, mainly because it's people talking about how great I am. But it looks like someone forgot to design the actual page.

The heart icon also appears differently on mobile screens since I'm using an ACSII character. Which means it turns into the default heart emoticon on different mobile operating systems:
[Image Heart Icon]

#### For Consideration
- Swap out with a SVG icon
- Use words instead of icon

- - -

## Story Behind This Site

![Benjamin Kinzer Story Behind This Site]({{ base.url }}/images/benjaminkinzer/v1-1/bk-story-behind-site.jpg)

I absolutely hate this page. It really should not live within the top level navigation. My thought was to document the process of this site and rapid prototyping with this page, but I think that can be better achieved with a Journal page, like the one you are viewing now.

#### For Consideration
- Swap out with a SVG icon
- Use words instead of icon

- - -

## Contact
People haven't had a difficult time finding how to contact me, so that is a success having the information at the bottom of the site. However I do believe I could make it easier for people to find a way to contact me, besides on the profile or bottom of the page.

- - -

## Navigation
[Image Navigation]
I had the intention of making the Navigation work more like breadcrumbs. I'm still excited about this idea and will be prototyping this in the next phase.

- - -

## Bigger Vision
My goal is to create an archive for my work, but also make it easy for anyone to either dive deeper or just stare at pretty pictures. My thinking is to create a site that functions like , but also provide a the ability to just see the Cliff Note version. But I will discuss this more in future posts. For now we will just try to adjust a few items outlined above.
