---
subjects:
  - Internet
  - Computers
status: todo
---
These three concepts are extremely important in web development.

- The client refers to the software that makes a request to the server. This is usually the user's web browser that makes a request to the website's server receiving computer, aka the user who is trying to access the webpage.

- The API (Application Programming Interface), refers to the interface that allows one application to communicate with another. Website APIs commonly use [[HTTP]] requests to allow communication between the user and server.

- The server, is the physical server (could be your computer, could be in the cloud, could be a physical server), that serves the webpage and/or JSON data to render the webpage for the client.

## SSR

These are two different ways a website can render on your computer. These methods can also be combined but we won't discuss that in this note, we will just discuss the overall description of what this means.

Lets start with the more traditional method, SSR.

**SSR** stands for server-side rendering, and that is when the server gives pure HTML that your web browser (client) renders.

So a typical interaction looks like this:

**Client -> HTTP request -> Server Gives HTML -> HTTP response -> Client**

Now obviously there are more processes involved due to HTTPS and TLS and other security protocols, but for the sake of this note, we will ignore those.

> [!IMPORTANT] SSR still uses JavaScript
> 
> Using SSR does not automatically mean the browser does not use any JavaScript at all, it could still use it to make buttons or elements interactive, make animations, and handle events.

## CSR

CSR, or client-side rendering, is the "modern" way that websites render on your computer, and it is used to make more interactive websites and applications.

When an API is involved, the client might send an HTTP request to an API endpoint on the server. The server processes the request and sends back a response, often containing JSON data.

And then your browser (client), uses the JavaScript to render the webpage using that JSON data.

So it might look more like this:

**Client -> HTTP request -> Server -> HTTP response -> JSON -> Client**