Back to the roots with Remix

The modern web would be different without rich client-side applications supported by powerful frameworks: React, Angular, Vue, Lit, and many others. These frameworks rely on client-side JavaScript, which is their core. However, there are other approaches to rendering. One of them (quite old, by the way) is server-side rendering entirely **without JavaScript**.
Let's find out if this is a good idea and how Remix can help us with it?

## Prerequisites

- Good understanding of JavaScript or TypeScript
- It would help to have experience with React, Redux, Node.js and writing FrontEnd and BackEnd applications
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- We prefer to use `VSCode`, but also cloud IDEs such as [codesandbox](https://codesandbox.io) (other IDEs are also ok)

## Agenda

- Introduction 📢
- Example Application 💻
- Theory 📕
  - Esbuild Experiment 🔬
- Remix Dive In 🏊‍♀️
- Summary 🥟

### Alex Korzhikov

![alex korzhikov photo](https://github.com/x-technology/PizzaScript/blob/main/assets/alex-black-white-open-source.png?raw=true)

Software Engineer, Netherlands

My primary interest is self development and craftsmanship. I enjoy exploring technologies, coding open source and enterprise projects, teaching, speaking and writing about programming - JavaScript, Node.js, TypeScript, Go, Java, Docker, Kubernetes, JSON Schema, DevOps, Web Components, Algorithms 👋 ⚽️ 🧑‍💻 🎧

- [AlexKorzhikov](https://twitter.com/AlexKorzhikov)
- [korzio](https://github.com/korzio)

### Pavlik Kiselev

![Pavlik](https://github.com/korzio/note/blob/master/docs/workshop/site/workshop/codelabs/assets/team/pavlik.jpg?raw=true)

Software Engineer, Netherlands

JavaScript developer with full-stack experience and frontend passion. He runs a small development agency [codeville.agency](https://codeville.agency/) and likes to talk about technologies they use: React, Remix and Serverless.

- [Pavlik Kiselev](https://www.linkedin.com/in/pavlik-kiselev-06993347/)
- [paulcodiny](https://github.com/paulcodiny)

# Code

- [Movies - CodeSandbox Project](https://codesandbox.io/p/sandbox/wandering-dream-xeomqw?file=%2Fapp%2Froutes%2Fmovies%2F%24movieId.reviews.tsx)
- [Movies - Github Repository](https://github.com/korzio/testcodesandbix)

## Remix Framework
- [Remix Framework](https://remix.run)

## Rendering Approaches
- ![Rendering Approaches](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/foundation.png?raw=true)

## Remix Rendering Approach
- Small demo

## Remix Rendering Approaches
- Server-side rendering + client-side hydration
- Pure server-side rendering

## Remix Blog Tutorial
- ![Remix Blog Tutorial](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/code-samples.png?raw=true)

## Building
- ![Building](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/build.png?raw=true)

## Esbuild Remix Experiment

> DIY Let's do Remix today with own hands!

Alex Korzhikov - March, 2023

- How Remix Works
  - [Example App](https://codesandbox.io/p/sandbox/wandering-dream-xeomqw)
- Esbuild Experiment
- Summary
  - Problems

### [How Remix Works](https://remix.run/docs/en/main/pages/technical-explanation)

- compiler - server side and client side app, alongside with manifest meta information?

![How Compiler Works](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/remix-compiler.png?raw=true)

- server
  - serves routes come from build
  - adapters to transform routes to a particular http server
  - controller and view (not a model) - each route can contain loader, action, and default component
- client
  - hydration

![How Server and Client Work](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/remix-server-and-client-work.png?raw=true)

### Esbuild Experiment

#### Goals

- Play around esbuild and compile javascript code
- Understand how remix works

#### Steps

![First Steps](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/esbuild-experiment-high-level.png?raw=true)

- dev routes server
- add esbuild, jsx
- ~~dev routes client~~
- react ssr

## Remix Routing
```
app/
    ├── routes/
    │   ├── about.tsx           // route is based on the static path
    │   ├── blog/               // route has an additional "/blog" segment in the URL
    │   │   ├── $postId.tsx     // dynamic params
    │   │   ├── categories.tsx  // static segments
    │   │   └── index.tsx       // index of the "/blog" directory
    │   ├── $.tsx               // splat route (catch-all routes)
    │   ├── blog.authors.tsx    // dot delimiter
    │   ├── blog.tsx            // layout for a regular route
    │   └── index.tsx
    └── root.tsx
```
- Optional segments and pathless routes, that are you not reflected in the URL

## Waterfall Loading (Problem)
- [Waterfall Loading Problem Code](https://gist.github.com/)

## Waterfall Loading (Solution)
- ![Waterfall Loading Solution](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/waterfall-solution.png?raw=true)

## Other Features
- Authentication
- SEO
- Error boundaries

## Promises
- Web standards
- Modern web app UX
- Better websites

## Results
- Navigation input
- Form-based mutations
- Optimistic updates
- Good UX by default

## How to Start
- Do the tutorials (blog or jokes app)
- Deploy to vercel.com
- Write about it

## Statement
- Remix is cool but use it wisely

## Summary

![State of current implementation](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/esbuild-experiment-outcome.png?raw=true)

## Feedback

Please [share your feedback](https://forms.gle/8UcN6H1VaWtekCaPA) on our workshop. Thank you and have a great coding!

If you like the workshop, you can become our [patron](https://www.patreon.com/xtechnology), yay! 🙏

## Links

- [Esbuild Remix Experiment](https://github.com/x-technology/back-to-the-roots-with-remix/tree/main/esbuild-experiment)
- [Remix](https://remix.run/)
- [React Streaming In Depth: NextJS! Remix! DIY!- Jack Herrington](https://www.youtube.com/watch?v=o3JWb04DRIs)
- [Fundamentals of Redux Course from Dan Abramov](https://egghead.io/courses/fundamentals-of-redux-course-from-dan-abramov-bd5cc867)
- [Test Remix App](https://github.com/korzio/testcodesandbix)

### Technologies

- remix
- javascript
- react
- esbuild