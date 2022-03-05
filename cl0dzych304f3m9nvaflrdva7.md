## I built a Link shortener using Remix and here's my experience!

A few days ago, I decided to try out [RemixJS](https://remix.run) and tried building a link shortener using it... cause if I create one more Todo List app, I'll lose my mind.
Here's my experience of using Remix till now.

## What is Remix?
Well, let me start with what Remix is. If you've used ReactJS before, you'd most probably have come across [React Router](https://reactrouterdotcom.fly.dev/docs/en/v6). Around a couple years ago, the founders of React Router decided to create a React framework on top of React Router. It originally needed a license, but last year, they decided to go open source! So now, it is something anyone can access.

## More about Remix?
I started following @[Kent C. Dodds](@kentcdodds), who is a part of the remix team, and he has a lot of livestreams where he talks about remix, and has a couple videos which really pushed me to try out remix. I highly recommend subscribing to his [Youtube Channel](https://www.youtube.com/c/KentCDodds-vids) and he has an amazing [Website](https://kentcdodds.com) also built using remix. It's amazing if you go through it, and you can find a really good video on it by Kent [here](https://youtu.be/owOZMwNPAyc).

## About the Link shortener
I decided to try Remix out by creating a Link shortener, because that was something simple yet I could experiment with concepts like authentication, data fetching and all that fancy stuff.
You can find the code [here](https://github.com/kavinvalli/remix-url-shortener).
First, I went through the [tutorials](https://remix.run/docs/en/v1/tutorials/blog) on Remix's docs which is a really good resource on starting with remix.

### Authentication
Then, I started off and decided to use Github for authentication. Now, I didn't want to Github OAuth by myself and didn't want to go through the work of having to manage tokens in the app, so I decided to use [Remix Auth](https://github.com/sergiodxa/remix-auth). It works really really well with Remix and has [support](https://github.com/sergiodxa/remix-auth/discussions/111) for a lot of strategies).
It took me a little while to get started with it cause, it doesn't really have good docs at the time but the examples were helpful. Now, the docs have improved a lot and you should be good to go pretty soon.

### Core Concepts
The Jokes tutorial covered most of the concepts I needed to build the url shortener. So, it didn't take me too long to complete the app. All the concepts, including db interaction, data fetching, form validation and submission was already stuff I'd read about in the tutorial so I would recommend going through that to get started with Remix.

## Conclusion
In the end, I had a great time getting started with Remix and I think it's definitely something I'll use more in the future.

Make sure to star the repo below and would love to know your experience with Remix after you give it a go in the comments!
You're welcome to use the shortener for your use!

%[https://github.com/kavinvalli/remix-url-shortener]