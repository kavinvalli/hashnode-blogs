## RITA - Batteries included starter for Adonis apps

People who've tried Laravel would know how easy it makes lives of developers. Then, came in [AdonisJS](https://adonisjs.com/) which is essentially just Laravel for Typescript developers. I've used both for a while now and love not having to go through long processes of setting up codebases from scratch.

One of my [seniors](https://github.com/dotangad), told me about [Inertia](https://inertiajs.com/) and we used it for a couple of projects with Laravel and it was amazing to be able to use Laravel with React. Essentially, Inertia is just a connector / glue between server-side and client-side frameworks.


> 
With Inertia you build apps just like you've always done with your server-side web framework of choice. You use your framework's existing functionality for routing, controllers, middleware, authentication, authorization, data fetching, and more.


> 
The only thing that's different is your view layer. Instead of using server-side rendering (eg. Blade or ERB templates), the views are JavaScript page components. This allows you to build your entire front-end using React, Vue or Svelte.

By using Inertia, I was able to pass data from my server side framework (Laravel) to my client side framework (ReactJS) as props which made it super easy to work with data since I had to no longer do the work of fetching data from REST or GraphQL APIs.

My senior created [LIRET](https://github.com/dotangad/liret) which uses Laravel and React with Inertia as an adapter with more features out of the box.

I finally came across [inertia-adonisjs](https://github.com/eidellev/inertiajs-adonisjs) which is a `Inertia.js AdonisJS Provider`. 

I recreated the LIRET stack but with AdonisJS and then came up [**RITA**](https://github.com/kavinvalli/rita)

RITA is a batteries-included starter for Adonis apps. The full form of Rita is `React Inertia Typescript Adonis`.

### Features
#### Backend
- AdonisJS
- Database (MySQL but you can change it very easily)
- Authentication
    - Email-Password
    - Github
    - Gmail
    - You can also add other providers very easily
- Admin Authorisation with Middleware support

#### Frontend
- Frontend with React and Typescript
- TailwindCSS setup
- Some built in components/hooks like `useTitle` and `TextInput` for simplicity
- Built in components for Authorisation validation like `<Admin>`, `<User>`, `<Authenticated>` and `<Guest>`

Using Inertia as a connector.

There are a few more features and you can find detailed instructions at the [Readme](https://rita.kavin.me).

Give the repo a star if you like it!


%[https://github.com/kavinvalli/rita]