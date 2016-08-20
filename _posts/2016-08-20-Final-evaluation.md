---
layout: post
title:  "GSoC: Final evaluation"
date:   2016-08-20
resume: Summer of code is ending
image: end.jpg
permalink: /blog/:year/:month/:day/:title
---

Hello!

Three months ago I started working with the frontend of Portus, on Google Summer of Code. Passed quickly, but I had many learnings, I met many people and made new friends!

I contributed the Portus basically in two ways: at the [system](https://github.com/SUSE/Portus/commits/master?author=msfernandes) and on the [site](https://github.com/SUSE/Portus/commits/gh-pages?author=msfernandes). Unfortunately, I couldn't finish all the tasks that I planned in my [project proposal](https://storage.googleapis.com/summerofcode-prod.appspot.com/gsoc/core_project/doc/1458137508_GoogleSummerofCodeProposal-ImprovetheUIofPortus.pdf?Expires=1471799951&GoogleAccessId=summerofcode-prod%40appspot.gserviceaccount.com&Signature=AW3BbKGteW14D69lGByyfbhfPw7JIBYKVAMvvtbhoxnuklCcMSCmJMTVPC3KEUe8Z8ISHFNsqOzf7131nNSlT3A4VmYBV68SvpN9QZXFvs7hCn5IdweAtm%2BuI25EVNy67kt4eUK%2Fc8A9uFwtWOGbajQfdLuoBTVLrstueqO7Fnu9nNyykn96S6z%2BHA5%2FX9nWz4Wi9AaX2BI9c%2F9RHn5ik329yPFKLq1VJ1hCclsd6R3%2B8vgTsyNo7sg5dWE9sG3WxEpveurYrj3Nhg09LkWNXXCS%2FSWV9bNP6cUIUw%2FQMEskFVSxsjna5WyhLd79y5O7OU0xWNpXW4eUjB%2FzGKfKsA%3D%3D) because some tasks took longer than I thought it would take, and Ruby on Rails is a new technology for me (although most of the tasks has been frontend, some needed work also on the backend). Some tasks have been listed in previous posts so I will not talk about all this here.

Let's start with the Refactoring of Assets structure that I started talking in my [last post](/blog/2016/06/30/Midterm-evaluation). It's always good when we are developing something, also think about performance. And in Portus many static files were downloaded and unused. So one of my goals for the Summer of Code was to solve this problem. After spending some time analyzing all code of Portus and separating what was being used and where it was being used I came to a solution using Rails Assets Pipeline. It's possible to make resources required only when their respective controller is called, so I separated the CSS and JS in files that the code is frequently used and in files that the code is used only on specific pages. Then  files with code common to most pages were requested on every page and the specifics CSS and JS were requested only when their controllers are called. For example, the "Pacific" source is only charged when used and not on every page as it was done.

The next task was develop the FAQ page and add a link to it in Protus:

<div class="post-img">
    <img class="img medium materialboxed" data-caption="FAQ Page" src="/images/faq-page.png">
</div>

And after finishing the job I'm doing at the moment I will make an improvement to the FAQ page: enable the click on anywhere in the tab with the question expand the answer.

Finally, the task that is giving more work: the dynamic filter mentioned in my last post! The hard part was just keeping the pagination and sorting of the tables while the dynamic filter was runing, but after some time researching I found an interesting way to do that (you can see in this [pull request](https://github.com/SUSE/Portus/pull/1016)). Another difficulty I encountered and what's making me take more time that I want to finalize the PR is when you need two filters on the same page. When I built the helpers, I did not think this possibility and now I'm having trouble leaving even more generic. But despite the difficulties, it is going well and we already have some results:

<div class="post-img">
    <img class="img medium materialboxed" data-caption="Filtering on search page" src="/images/filtering.gif">
</div>

Well, this is my last post for GSoC and I would like to thank this great opportunity to [@mssola](https://github.com/mssola) and [@flavio](https://github.com/flavio) by mentoring and patience. I would also like to thank the [openSUSE](https://github.com/openSUSE) support and all the other [mentors](https://github.com/openSUSE/mentoring/issues) who made this experience so important to my life! Thank you :)