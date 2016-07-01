---
layout: post
title:  "GSoC: Midterm evaluation"
date:   2016-06-30
resume: First part of GSoC is done. See what I did!
image: portus.png
permalink: /blog/:year/:month/:day/:title
---

Hi! :)

The GSoC mid-term evaluation was done this week, so I will write about this first part of the Summer of Code! As you may know, I'm working on [Portus](http://port.us.org) user interface and here is a list of the work that I've done until today (you can follow these links and see some screenshots):

<div class="post-list">
  <ul>
  	<li><a href="https://github.com/SUSE/Portus/pull/773">Added logout button and search form on small screens (before GSoC).</a></li>
  	<li><a href="https://github.com/SUSE/Portus/pull/776">Changed activity messages to fill all horizontal space available (before GSoC).</a></li>
  	<li><a href="https://github.com/SUSE/Portus/pull/781">Updated alert messages.</a></li>
  	<li><a href="https://github.com/SUSE/Portus/pull/916">Proposed a new topbar to Portus website/blog.</a></li>
    <li><a href="https://github.com/SUSE/Portus/pull/924">Refactored admin dashboard on small screens.</a></li>
    <li><a href="https://github.com/SUSE/Portus/pull/924">Added namespaces and teams search.</a></li>
    <li><a href="https://github.com/SUSE/Portus/pull/930">Refactored documentation lateral menu.</a></li>
  </ul>
</div>

Unfortunately, I could not finish all the scheduled issues of the first part of the Summer of Code because some of them were more difficult than I expected. "Refactor tables on small screens" (mentioned on my [last post](/blog/2016/06/05/First-contributions)), for example, gave me a lot of headache because almost all tables in Portus are updated using AJAX and the JS library that I was using ([FooTable](http://fooplugins.com/plugins/footable-jquery/)) was needed to be executed in every update, but when it happen some elements on the tables were duplicated. Now, I'll search for another plugin or maybe a pure CSS solution. Other issue that was bigger than we (I and [@mssola](https://github.com/mssola)) expected is the "[Improve filtering](https://github.com/SUSE/Portus/issues/454)", that is a dynamic filtering of namespaces, teams and users, but the difficult here is the conflict with the pagination. Therefore, the solution should be a compromise between client-backend side while allowing pagination and filtering.

Now, I'm working on "Serve assets only when used" and on this issue I'll refactor the way that Portus loads CSS and JS files. Today, only one CSS/JS file is served, which means that all style and javascript code is loaded in every page, even if the code is not used. So, my approach on this issue will be unify the common CSS/JS and only this one will be served in all pages, after that, I'll create specific CSS/JS for each controller. If only one page need some code, this code will be served only for this page :)

After that I'll follow this issue list:

<div class="post-list">
  <ul>
  	<li><strong>Fix anchor on gh-pages:</strong> one of my pull requests introduced this bug. :(</li>
  	<li><strong>Create a help section:</strong> it will be a FAQ page and some links to the documentation of Portus.</li>
  	<li><strong>Improve filtering:</strong> as mentioned previously on this post.</li>
  	<li><strong>Explore feature:</strong> show public images even if the user is logged out.</li>
  	<li><strong>Refactor tables on small screen:</strong> as mentioned previously on this post.</li>
  	<li><strong>Improve dashboard interface:</strong> allow searching and sorting repositories in the dashboard page. Also, show only a fixed amount of rows with a pagination.</li>
  	<li><strong>Migrate Portus LESS to SASS:</strong> only if we have the time. :)</li>
  </ul>
</div>

So, this was a summary of my first part of Summer of Code! In my next post I’ll tell you about my amazing experience in Nuremberg, for the [openSUSE Conference](https://events.opensuse.org/conference/oSC16)! See you :)