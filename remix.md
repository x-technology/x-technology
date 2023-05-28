---
title: XTechnology Workshop - Back to the roots with Remix
---

[![XTechnology - Technology is beautiful, let's discover it together!](https://user-images.githubusercontent.com/1259644/139526072-c2df5b3f-86b3-40eb-a91a-e51a307269ec.png)](https://xtechnology.dev/)

<style type="text/css">
  h1:first-child {
    display: none;
  }

  img[alt="andrew reddikh"] {
    filter: grayscale(100%);
  }

  img[alt="microservices graph"] {
    width: 500px;
  }
  /* twitter button */
  .twitter-btn {
    width: 200px;
    display: inline-block;
    overflow: hidden;
    text-align: left;
    white-space: nowrap;
    vertical-align: top:
    zoom: 1;
    font-size: 13px;
    line-height: 26px;
    font-family: "Helvetica Neue",Arial,sans-serif;
  }
  .twitter-btn a {
    height: 28px;
    padding: 1px 10px 1px 9px;
    border-radius: 4px;
    position: relative;
    font-weight: 500;
    color: #fff;
    cursor: pointer;
    background-color: #1b95e0;
    border-radius: 3px;
    box-sizing: border-box;
    display: inline-block;
    text-decoration: none;
  }
  .twitter-btn a:hover {
    background-color: #0c7abf;
  }
  .twitter-btn a i {
    width: 18px;
    height: 18px;
    top: 4px;
    position: relative;
    display: inline-block;
    background: transparent 0 0 no-repeat;
    background-image: url(data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20viewBox%3D%220%200%2072%2072%22%3E%3Cpath%20fill%3D%22none%22%20d%3D%22M0%200h72v72H0z%22%2F%3E%3Cpath%20class%3D%22icon%22%20fill%3D%22%23fff%22%20d%3D%22M68.812%2015.14c-2.348%201.04-4.87%201.744-7.52%202.06%202.704-1.62%204.78-4.186%205.757-7.243-2.53%201.5-5.33%202.592-8.314%203.176C56.35%2010.59%2052.948%209%2049.182%209c-7.23%200-13.092%205.86-13.092%2013.093%200%201.026.118%202.02.338%202.98C25.543%2024.527%2015.9%2019.318%209.44%2011.396c-1.125%201.936-1.77%204.184-1.77%206.58%200%204.543%202.312%208.552%205.824%2010.9-2.146-.07-4.165-.658-5.93-1.64-.002.056-.002.11-.002.163%200%206.345%204.513%2011.638%2010.504%2012.84-1.1.298-2.256.457-3.45.457-.845%200-1.666-.078-2.464-.23%201.667%205.2%206.5%208.985%2012.23%209.09-4.482%203.51-10.13%205.605-16.26%205.605-1.055%200-2.096-.06-3.122-.184%205.794%203.717%2012.676%205.882%2020.067%205.882%2024.083%200%2037.25-19.95%2037.25-37.25%200-.565-.013-1.133-.038-1.693%202.558-1.847%204.778-4.15%206.532-6.774z%22%2F%3E%3C%2Fsvg%3E);
  }
  .twitter-btn a span {
    margin-left: 4px;
    white-space: nowrap;
    display: inline-block;
    vertical-align: top;
    zoom: 1;
  }
</style>

<div class="twitter-btn">
  <a href="https://twitter.com/XTechnology5/status/1662440871936114688"><i></i></a>
</div>

# Back to the roots with Remix

The modern web would be different without rich client-side applications supported by powerful frameworks: React, Angular, Vue, Lit, and many others. These frameworks rely on client-side JavaScript, which is their core. However, there are other approaches to rendering. One of them (quite old, by the way) is server-side rendering entirely **without JavaScript**.
Let's find out if this is a good idea and how Remix can help us with it?

## Prerequisites

- Good understanding of JavaScript or TypeScript
- It would help to have experience with React, Redux, Node.js and writing FrontEnd and BackEnd applications
- [Preinstall Node.js, npm](https://nodejs.org/en/download/)
- We prefer to use `VSCode`, but also cloud IDEs such as [codesandbox](https://codesandbox.io) (other IDEs are also ok)

## Agenda

- Introduction 📢
- Demo - Example Application 💻
- About Remix 📕
  - How Remix Works 🛠️
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

<iframe src="https://wall.sli.do/event/1Z6LF8MxZFNjo1E2PBg9VD?section=414edbc6-a745-42d6-a140-f0f827e8d5fa" width="50%" height="400px" ></iframe>

- [Remix Framework](https://remix.run)

## Demo - Example Application

### Waterfall Loading (Problem)
- [Waterfall Loading Problem Code](https://gist.github.com/)

```jsx
import { useParams } from "react-router";

type useQueryType = { <T>(x: string): { data: T | null } };
const useQuery: useQueryType = (type) => ({ data: null });

type SalesType = { id: number; overdue: string; dueSoon: string };
type InvoiceType = { id: number; user: string; value: string; details: string };

// URL: /sales/invoices/1
export const InvoicesPage = () => {
  return (
    <div>
      <Invoices />
    </div>
  );
};

const Invoices = () => {
  const { data: invoices } = useQuery<InvoiceType[]>("invoices");
  if (!invoices) return null;
  const { invoiceId } = useParams();
  return (
    <>
        <ul>
          {invoices.map((invoice: InvoiceType) => (
            <li key={invoice.id}>
              <a href={`/invoices/${invoice.id}`}>{invoice.user} {invoice.value}</a>
            </li>
          ))}
        </ul>
        {invoiceId && <Invoice id={Number(invoiceId)} />}
    </>
  );
};

type InvoiceProps = { id: number };
const Invoice = ({ id }: InvoiceProps) => {
  const { data: invoice } = useQuery<InvoiceType>(`invoices/${id}`);
  if (!invoice) return null;
  return (
    <div>
      {invoice.user}: {invoice.details}
    </div>
  );
};
```

### Waterfall Loading (Solution)

![Waterfall Loading Solution](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/waterfall-solution.png?raw=true)

### Remix Rendering Approach
- Small demo

## About Remix

> a modern full stack web framework

```jsx
import { json } from "@remix-run/node"; // or cloudflare/deno

export async function loader() {
  const res = await fetch("https://api.github.com/gists");
  const gists = await res.json();

  return json(
    gists.map((gist) => ({
      description: gist.description,
      url: gist.html_url,
      files: Object.keys(gist.files),
      owner: gist.owner.login,
    }))
  );
}

export default function Gists() {
  const gists = useLoaderData<typeof loader>();

  return (
    <ul>
      {gists.map((gist) => (
        <li key={gist.id}>
          <a href={gist.url}>
            {gist.description}, {gist.owner}
          </a>
          <ul>
            {gist.files.map((key) => (
              <li key={key}>{key}</li>
            ))}
          </ul>
        </li>
      ))}
    </ul>
  );
}
```

### Rendering Approaches

![Rendering Approaches](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/foundation.png?raw=true)

### Remix Rendering Approaches
- Server-side rendering + client-side hydration
- Pure server-side rendering

### Remix Blog Tutorial

![Remix Blog Tutorial](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/code-samples.png?raw=true)

```jsx
// https://github.com/remix-run/examples/blob/main/_official-blog-tutorial/app/routes/posts/index.tsx
import { json } from "@remix-run/node"
import { Link, useLoaderData } from "@remix-run/react"

import { getPosts } from "~/models/post.server"

export const loader = async () => json({ posts: await getPosts() })

export default function Posts() {
  const { posts } = useLoaderData<typeof loader>()
  return (
    <main>
      <h1>Posts</h1>
      <Link to="admin" className="text-red-600 underline">Admin</Link>
      <ul>
        {posts.map((post) => (
          <li key={post.slug}>
            <Link to={post.slug} className="text-blue-600 underline">{post.title}</Link>
          </li>
        ))}
      </ul>
    </main>
  )
}
```

### [How Remix Works](https://remix.run/docs/en/main/pages/technical-explanation)

- compiler - server side and client side app, alongside with manifest meta information

> *a compiler for React Router*

![How Compiler Works](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/remix-compiler.png?raw=true)

- server
  - serves routes come from build
  - adapters to transform routes to a particular http server
  - controller and view (not a model) - each route can contain `loader, action & default component`
- client
  - hydration
  - web worker
  - forms
  - session
  - cookies
  - auth

![How Server and Client Work](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/remix-server-and-client-work.png?raw=true)

### Remix Routing
```bash
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

## Other Features
- Authentication
- SEO
- Error boundaries
- Stacks

![remix error boundaries user interface example with message something went wrong](https://remix.run/docs-images/error-boundary.png)

## Promises
- Web standards
- Modern web app UX
- Better websites

## Results
- Navigation input
- Form-based mutations
- Optimistic updates
- Good UX by default

### Esbuild Experiment

> DIY Let's do Remix today with own hands!

- [Example App](https://codesandbox.io/p/sandbox/wandering-dream-xeomqw)

#### Goals

- Play around esbuild and compile javascript code
- Understand how remix works

#### Steps

![First Steps](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/assets/esbuild-experiment-high-level.png?raw=true)

- dev routes server
- add esbuild, jsx
- ~~dev routes client~~
- react ssr
- demo esbuild experiment

![State of current implementation](assets/esbuild-experiment-outcome.png)

#### Build

![Build](https://github.com/x-technology/back-to-the-roots-with-remix/blob/main/remix-s/src/assets/build.png?raw=true)

```jsx
// app/routes/posts/index.tsx
var posts_exports = {};
__export(posts_exports, {
  default: () => Posts,
  loader: () => loader5
});
var import_node7 = require("@remix-run/node"),
    import_react7 = require("@remix-run/react");
var import_jsx_dev_runtime7 = require("react/jsx-dev-runtime"),
    loader5 = async () => (0, import_node7.json)({ posts: await getPosts() });
function Posts() {
  let { posts } = (0, import_react7.useLoaderData)();
  return /* @__PURE__ */ (0, import_jsx_dev_runtime7.jsxDEV)("main", { children: [
    /* @__PURE__ */ (0, import_jsx_dev_runtime7.jsxDEV)("h1", { children: "Posts" }, void 0, !1, {
      fileName: "app/routes/posts/index.tsx"
    }, this),
    /* @__PURE__ */ (0, import_jsx_dev_runtime7.jsxDEV)(import_react7.Link, { to: "admin", ...
    }, this),
    /* @__PURE__ */ (0, import_jsx_dev_runtime7.jsxDEV)("ul", { children: posts.map((post) => ...
    }, this) }, post.slug, !1, {
      fileName: "app/routes/posts/index.tsx"
    ...
}
```

```jsx
import { createPost } from "~/models/post.server"

export const action = async ({ request }: ActionArgs) => {
  const formData = await request.formData()

  const title = formData.get("title")
  if (!title) return json({ error: "Title is required" })

  await createPost({ title })

  return redirect("/posts/admin")
};

export default function NewPost() {
  const transition = useTransition()
  const isCreating = Boolean(transition.submission)

  return (
    <Form method="post">
      <label>
        Post Title:{" "}<input type="text" name="title" />
      </label>
      <button type="submit" disabled={isCreating}>
        {isCreating ? "Creating..." : "Create Post"}
      </button>
    </Form>
  );
}
```

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
- [Remix Community](https://remix.run/docs/en/1.16.1/pages/community)

### Technologies

- remix
- javascript
- react
- esbuild