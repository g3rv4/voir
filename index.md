---
layout: default
---
# <a id="#top">@SocialVoir</a>

Do you want to see somebody else's timeline? There's a bot for that!

## FAQs (aka: things I think make sense to talk about)

* [How can I see an account's timeline?](#see-somebodys-timeline)
* [How can I stop seeing someone's timeline?](#stop-seeing-a-timeline)
* [Why are you asking me to give you write access to my account?](#why-do-you-need-my-account)
* [I don't want to give *you* access to my account. Can I still use it?](#can-i-use-it-without-giving-you-access)
* [How can I revoke your access to my account?](#revoke-access)
* [How does this work?](#how-does-it-work)
* [Can it be used with evil purposes?](#do-not-be-evil)
* [How do you want to use it?](#it-can-be-useful)
* [Can I see the source code?](#source-code)
* [Who built this bot?](#who-built-it)

## Issues
* [My lists are missing people](#missing-people)
* [The first lists worked fine but now my new lists have 0 members](#zero-members)
* [How can I update a list?](#update-a-list)

## FAQs

#### <a id="see-somebodys-timeline">What should I do if I want to see @twitter's timeline?</a>

1. Give this app read/write access to your account by visiting [setup.voir.social](https://setup.voir.social) ([why?](#why-do-you-need-my-account)) (and also... it doesn't have to be your main one)
2. Compose a tweet saying `@SocialVoir voir twitter` (or `@SocialVoir <anything> voir twitter`)
3. The bot is going to create a private list on your account containing all the people @twitter follows... and if you see that list, you'd see @twitter's timeline!

There're a few things missing though:

* People with private accounts will not be included on the list (so @twitter would see those tweets, but you wouldn't)
* If @twitter follows both @accountA and @accountB, they would see their interactions (when @accountA replies to a tweet from @accountB). This is not shown when both @accountA and @accountB are on a list

[Back to the top](#top)

### <a id="stop-seeing-a-timeline">What should you do if you don't want that list anymore?</a>

You can do any of these:

* Delete the list from your twitter account
* Compose a tweet saying `@SocialVoir unvoir twitter`. That will remove the list from your account

[Back to the top](#top)

### <a id="why-do-you-need-my-account">Why are you asking for access to my account?</a>

When I started coding this, I thought I would just create the lists on the bot's account... but I hit the twitter API rate limits very quickly. When you give me write access to your account, I can create lists that belong to you, and then scale better. Your account can add up to 1000 members Rate limits are per application/account, so if the bot does lots of requests on your behalf (and it has to, I'll write a blog post where I explain the many issues I found with twitter's API) and reaches a rate limit, that shouldn't affect you in any way.

[Back to the top](#top)

### <a id="can-i-use-it-without-giving-you-access">I don't want to give *you* access to my account. Can I still use it?</a>

Yes! you can... it's [open source](https://github.com/g3rv4/socialvoir) and there's [a docker image](https://hub.docker.com/r/g3rv4/socialvoir/) that you can even run on your computer (without opening any ports at all)

[Back to the top](#top)

### <a id="revoke-access">What should I do if I don't want this app to have access to my account?</a>

* Go to [your authorized apps at twitter](https://twitter.com/settings/applications)
* Revoke access to `Social Voir`

[Back to the top](#top)

### <a id="how-does-it-work">How does it work?</a>

This is pretty simple... who you follow, and who you followers are is all public information (so if you had lots of free time and wanted to see @twitter's timeline, you could just check who they're following and just follow the same people).

What this bot does, is use Twitter's API to retrieve who the account you're interested in is following, and then it creates a list on your account. Then, all you have to do is check out that list... that's all!

[Back to the top](#top)

### <a id="do-not-be-evil">Can it be used with evil purposes?</a>

A coworker was a bit concerned about trolls finding new victims based on their previous victims. It's true that it can be used for that. But IMO the problem is that people block accounts and then feel safer, while in reality, people you block can go into incognito mode (don't even need to create a new one) and still see your tweets, your followers and who you follow.

As usually people that want to do evil things have the time (and often also the resources) to go into their victims' accounts and stalk them, I'm still moving forward with this. I hope that it helps bring awareness of how public our accounts are (and what little the block functionality really does).

[Back to the top](#top)

### <a id="it-can-be-useful">How do you want to use it?</a>

One of the amazing perks I got at my new job was working with a group of extremely brilliant/passionate/caring/thoughtful people. When I followed them on twitter, I realized that twitter became way more interesting for me.

Now, I'd like to see what *they* see when they're using twitter... I expect this to let me find interesting accounts, and get me yet more value out of twitter!

[Back to the top](#top)

### <a id="source-code">Can I see the source code?</a>

Be my guest! You can find it on github, [g3rv4/socialvoir](https://github.com/g3rv4/socialvoir). There are lots of things missing, PRs welcome :) also, I'm running it as a docker image that [you can find here](https://hub.docker.com/r/g3rv4/socialvoir/) (you need to set up the environment variables... and you'd have to figure those out from the source code)

[Back to the top](#top)

### <a id="who-built-it">Who built this?</a>

The idea came from [this tweet from @BenedictEvans](https://twitter.com/BenedictEvans/status/833107860913430529) (retweeted by my manager, see? seeee?). I'm Gervasio, you can find me on twitter at [@g3rv4](https://twitter.com/g3rv4) or on [my blog](https://g3rv4.com)

[Back to the top](#top)

## Issues

### <a id="missing-people">My lists are missing people</a>

Your lists will always miss people with private accounts. Also, once 1000 accounts have been added to your lists, you can't add more for 24 hours. Just wait and then issue the same command (if you get an error saying that the status is a duplicate, you can add anything before the `voir` keyword)

[Back to the top](#top)

### <a id="zero-members">The first lists worked fine but now my new lists have 0 members</a>

Once you've added 1000 accounts to your lists, twitter doesn't let you add more accounts to your lists. You just have to wait... but if you've added 1000 people, you definitely have some interesting reading to do :)

[Back to the top](#top)

### <a id="update-a-list">How can I update a list?</a>

Lists are created once and never updated. If you do tweet `@SocialVoir voir account` (and you're already watching @account's feed), that's going to take care of updating it.

[Back to the top](#top)
