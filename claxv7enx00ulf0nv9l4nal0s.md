# Why I think the t3 stack is the next big thing in the JS... oh wait... the TS ecosystem?

There is this new stack in the open, the T3 stack, started by Theo, CEO of ping.gg and an ex-Twitch employee. I came across it when I was taking a look at tRPC and was amazed by how efficient, it made me while creating an app.
First of all, what is tRPC.

## What is the T3 Stack?

Quoting the website, *"We made create-t3-app to do one thing: Streamline the setup of typesafe Next.js apps WITHOUT compromising modularity"* which is so true. It is a stack which just works out of the box, but is yet so customisable. Just pick what you want to use and get up and running! It consists of:

*   [Next.JS](https://nextjs.org/)
*   [tRPC](https://trpc.io)
*   [Tailwind CSS](https://tailwindcss.com/)
*   [TypeScript](https://www.typescriptlang.org/)
*   [Prisma](https://prisma.io/)
*   [NextAuth.js](https://next-auth.js.org/)

## Next.JS

Ever since I gave Next.JS a try, it has been one of my favourite frameworks to
use. I have given so many more React frameworks a try, but Next.JS just works
for me.

> Next.js offers a lightly opinionated, heavily optimized approach to creating applications using React. From routing to API definitions to image rendering, we trust Next.js to lead developers toward good decisions.

## tRPC

tRPC is one of the best ways, in my opinion to create a fully typesafe API. API Routes allow us to build fullstack routes easier and faster. There are alternatives like GraphQL CodeGen but they essentially are a build step which generate types based on your GraphQL, which is kind of eh. tRPC just allows you to build it without an intermediate step. The following screenshot from the tRPC website just explains why tRPC.

![Why tRPC](<https://cdn.hashnode.com/res/hashnode/image/upload/v1669448172146/O1W\_t\_pQS.png> align="left")

You can read more about tRPC at [trpc.io](https://trpc.io).

## Tailwind CSS

For those, who don't know what Tailwind is, I have a blog post on it and how to
get started with tailwind [here](https://livecode247.com/start-with-your-first-tailwind-css-project).

## TypeScript

TypeScript isn't optional in the T3 stack and it is probably one of the best
things. Once you give TypeScript a try, you will not be able to go back to
Javascript. You will blow your head off trying to find the right data to pass
into a function, or trying to find why and where you have an error in your app
because it is the wrong type.

> Typesafety makes you faster. If you’re not convinced, [you might be using TypeScript wrong…](https://www.youtube.com/watch?v=RmGHnYUqQ4k)

## Prisma

Prisma is one of the best database adapters for TypeScript out there. It just
makes it so easy to work with SQL. It generates all the types for you as well
which is a big plus point, as it guarantees and continues the T3 Axiom of
end-to-end typesafety from your database to your app.
It also provides an awesome GUI called the Prisma Studio.

## NextAuth

Next Auth makes it very easy to plugin authentication into your NextJS application. It comes with many adapters which just work for you out of the box and is very simple to work with Prisma.

## Why I recommend the T3 stack?

First of all, type safety. TypeScript was a huge revolution when it came out in 2012 because of this reason. It just make you so much faster and efficient if you start using it right. The autocompletes, the hover documents, the red squiggly lines just make it much much easier to write code.

`create-t3-app` makes it easier to manage the *modularity and simplivity* in code while starting off. It just doesn't add everything.

> Everything added to create-t3-app should solve a specific problem that exists within the core technologies included. This means we won’t add things like state libraries (zustand, redux) but we will add things like NextAuth.js and integrate Prisma and tRPC for you.

## Resources to get started with the T3 stack

*   [Create T3 App Documentation](https://create.t3.gg/en/introduction)
*   [**The BEST Stack For Your Next Project** Video](https://www.youtube.com/watch?v=PbjHxIuHduU)
*   [**Build a Blog With the T3 Stack - tRPC, TypeScript, Next.js, Prisma, Zod** Video](https://www.youtube.com/watch?v=syEWlxVFUrY)

## References

*   [trpc.io](https://trpc.io/)
*   [Chris Bautista: Making typesafe APIs easy with tRPC](https://www.youtube.com/watch?v=2LYM8gf184U)
*   [create.t3.gg Github](https://github.com/t3-oss/create-t3-app)
*   [create.t3.gg](https://create.t3.gg)