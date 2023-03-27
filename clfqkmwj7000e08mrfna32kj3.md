---
title: "Master NextJS 13 Data Fetching with this Step-by-Step Guide"
seoDescription: "Discover NextJS 13's improved data fetching and management with fetch API, Server Components, and tips for static and dynamic data."
datePublished: Mon Mar 27 2023 08:32:42 GMT+0000 (Coordinated Universal Time)
cuid: clfqkmwj7000e08mrfna32kj3
slug: demystifying-data-fetching-in-nextjs-13
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679905873039/79efb7a5-4dac-4f0d-8e07-bce8aa5cb0cf.png
tags: javascript, web-development, reactjs, frontend-development, nextjs

---

The release of NextJS 13 brought about a plethora of new and impressive features, with one standout being the updated data fetching and management process. The fetch API replaced the more complicated functions, including `getServerSideProps`, `getStaticProps`, and `getInitialProps`.

## Video

If you prefer watching a video, you can check out the Youtube video posted on the same

%[https://youtu.be/CYCn1I_kvjc] 

## fetch() API

React recently introduces support for [async/await in Server Components](https://github.com/acdlite/rfcs/blob/first-class-promises/text/0000-first-class-support-for-promises.md). You can now write Server Components using standard JavaScript await syntax by defining your component as an async function and that is what turned out to be a big plus point for NextJS 13.

## Server Components

This is all you need to do to fetch data in NextJS now:

```typescript
import { Post } from "@/lib/types";
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

const getPosts = async (): Promise<Post[]> => {
  const data = await fetch("https://jsonplaceholder.typicode.com/posts");
  const posts = await data.json();

  return posts;
};

export default async function Posts() {
  const posts = await getPosts();
  console.log(posts);

  return (
    <div className={inter.className}>
      <h1>Posts</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}
```

The data is no more serialised so you can pass any type of data, including Dates, Maps, Sets, etc.

Also, note the fact that you no longer need to do this on the page level, like if you did before using `getStaticProps` or `getServerSideProps`. You can do this inside any component

## Client Components

For now, if you need to fetch data in a Client Component, NextJS 13 recommends using a third-party library such as [SWR](https://swr.vercel.app/) or [React Query](https://tanstack.com/query/v4).

React also introduced the [`use`](https://github.com/acdlite/rfcs/blob/first-class-promises/text/0000-first-class-support-for-promises.md#usepromise) hook that accepts a promise conceptually similar to await. use handles the promise returned by a function in a way that is compatible with components, hooks, and Suspense.

```typescript
"use client";

import { Post } from "@/lib/types";
import { Inter } from "next/font/google";
import { use } from "react";

const inter = Inter({ subsets: ["latin"] });

const getPosts = async (): Promise<Post[]> => {
  const data = await fetch("https://jsonplaceholder.typicode.com/posts");
  const posts = await data.json();

  return posts;
};

export default function ClientPosts() {
  const posts = use(getPosts());

  return (
    <div className={inter.className}>
      <h1>Posts</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}
```

## Static Data Fetching

`fetch` by default caches the data. So, even if the data from the API changes, when you refresh the page, the site doesn't update the data. This works great for sites which have static data which seldom changes. The example above demonstrates how to do this because it is the same as doing

```typescript
fetch("https://jsonplaceholder.typicode.com/posts", {
  cache: "force-cache",
});
```

## Dynamic Data Fetching

You can tell the `fetch` API to never cache the data by changing `force-cache` to `no-cache` or `no-store`(both signify the same in NextJS).

```typescript
fetch("https://jsonplaceholder.typicode.com/posts", {
  cache: "no-cache"
});
```

## Dynamic Params Data Fetching

Say, you link all the posts to another page `/posts/[postId]` and fetch the data here once you're in there. You'd do something like this:

```typescript
// app/posts/[postId]/page.tsx

import { Post } from "@/lib/types";
import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

// params: {
//   postId: aksdjlkjasd
// }

const getPost = async (id: string): Promise<Post> => {
  const data = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
  const post = await data.json();

  return post;
};

export default async function PostPage({
  params: { postId },
}: {
  params: {
    postId: string;
  };
}) {
  const post = await getPost(postId);
  return (
    <div className={inter.className}>
      <h1>{post.title}</h1>
      <p>Post ID: {postId}</p>
      <p>{post.body}</p>
    </div>
  );
}
```

Now, this works great, but when you try to build it, look at the response:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679905145318/c65e6c26-2761-4136-83e6-e3cbc3d57c73.png align="center")

It says that `/posts/[postId]` is server-side rendered at runtime even though `/posts` is static. This is because NextJS doesn't know what all routes(postIds) exist. So, to enhance this further, you can add this function to the `/posts/[postId]/page.tsx` page

```typescript
export const generateStaticParams = async () => {
  const data = await fetch("https://jsonplaceholder.typicode.com/posts");
  const posts = await data.json();

  return posts.map((post: Post) => ({
    params: {
      postId: post.id.toString(),
    },
  }));
};
```

This now tells NextJS, that all these `postId`s exist and we want it to statically generate them at build time if possible. Now, if we try rebuilding the app, this happens

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1679905387382/e9f4a8c8-9868-49fc-b5c0-a673fac91b86.png align="center")

Now, see that `/posts/[postId]` is static HTML + JSON! And, that would further optimise your app really well.

## Revalidating Data

Say, your app is not fully dynamic but still sometimes the data does change, you can add this to your `/posts/[postId]/page.tsx` page

```typescript
export const revalidate = 3600; // in seconds
```

This will tell NextJS to revalidate the data every hour. And the interesting this is, you can do this on the page level as well as the layout level.

You can also do this per fetch by tweaking the fetch call as follows

```typescript
fetch("https://jsonplaceholder.typicode.com/posts", {
  next: {
    revalidate: 3600,
  },
});
```

And that is it!

## Conclusion

It takes a while to wrap your head around all this, but this is what NextJS does so well and one of the biggest plus points about it, and once you get a hold of it, it's really powerful.

You can find all the code over here

%[https://github.com/kavinvalli/data-fetching-next13] 

Do give the video a look if you like that more, and stay tuned for more such posts!

## Reference Links

* [NextJS 13 Docs](https://beta.nextjs.org/docs)
    
* [NextJS 13 Data Fetching Docs](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbEt2ZTlmUXk4VFBWYzBZQWZlN1ZDZWFWX3ZHZ3xBQ3Jtc0tub3NFNmZoQ2tqc09SRUM0N2kwYnNQOEF0em4wSW52QzRhXzF5UDRKTTA1NmdjMUNfYTllekRMWHQwcEdoMkV6dk0zVU4wQ3VrWk1zME1nQzNNYlhKUTRRNUxOSXd6Qm9fUjFhbWJrZVUtUGp0cXRLQQ&q=https%3A%2F%2Fbeta.nextjs.org%2Fdocs%2Fdata-fetching%2Ffetching&v=CYCn1I_kvjc)
    
* [`use` hook in React](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbk1xRWc3VFpONm1fQTl2b0lOXzNnNUswcVlSd3xBQ3Jtc0trZ0MyRnVvamZ0eDZzMlRHeExRTklYS2xDeU5pVDB4amZTVFQwR0lYUy13eERGcmVrMXNORzNGWVRMNTN0aE9IVjdiaUZaNko0S2tZR2pKUG1WUDJGSFR6MmtCNm05X3IxaU9FRUU3T2lNZFRsZktTcw&q=https%3A%2F%2Fgithub.com%2Facdlite%2Frfcs%2Fblob%2Ffirst-class-promises%2Ftext%2F0000-first-class-support-for-promises.md%23usepromise&v=CYCn1I_kvjc)
    
* [SWR](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbnEwZ1BvMjhuNjZDUXozbVc1Um9oSndjLTQyUXxBQ3Jtc0ttV1dWMFpkS2JXdGNCbXJDOTk3RWZDbG9Kb19hSWdLMnFLVjJEWXplcG1XTWUwZnNpN29jMDVPQVhpVGMzV2g4TTg0dWlXYkNaMlhaVEdmakJqODduc05LbFVQWG9MOGlOZVFkbVJTbXdheGkxWTRLRQ&q=https%3A%2F%2Fswr.vercel.app%2F&v=CYCn1I_kvjc)
    
* [React Query](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbjlFdGVLVGpvZkUzQk9LRkc3cHZCRWxSZmlkZ3xBQ3Jtc0tuNWFfNWwyaEdHTk5nNk9zZWJwd0Fnd193ajh0dWlVODB3ejd0R3NDRjFLZUxHbEEyU1ljTFEwWWRiTWZvVzRNbnZqQUZfeUVlZkU4RDVpNEVkWXpGbEhhTUJtSDA3VVZSanRCYm40RmFSMkJ4b29yUQ&q=https%3A%2F%2Ftanstack.com%2Fquery%2Fv4&v=CYCn1I_kvjc)