# What is progressive rendering?

This is a set of techniques used to improve the performance of a webpage to render content for display as quickly as possible.

Examples:

- Lazy loading of images - images are not loaded all at once

- Prioritizing visible content - include only the minimum CSS/content/scripts needed for the amount of page that would be rendered in the users browser first to display as quickly as possible

- Async HTML fragments - flushing parts of the HTML to the browser

## Async fragments

Without progressive HTML rendering, a server/client waterfall chart might be similar to the following:

![async fragments](https://tech.ebayinc.com/assets/Uploads/Blog/2014/12/single-flush.png)

Because the HTML is not flushed until all back-end services are completed, the user will be staring at a blank screen for a large portion of the time.

A simple trick is to improve the responsiveness of a website is to flush the head section (links to the external CSS, page header, navigation) immediately.

![async fragments flush sooner](https://tech.ebayinc.com/assets/Uploads/Blog/2014/12/flush-head.png)

Instead of flushing only the head early, it is often beneficial to flush multiple times before ending the response.

![async fragments at a complex page](https://tech.ebayinc.com/assets/Uploads/Blog/2014/12/page-diagram.png)

Each fragment is assigned a number based on the order that it appears in the HTML document.

One caveat with out-of-order flushing is that it requires JavaScript running on the client to move each out-of-order fragment into its proper place in the DOM. Thus, you would only want to enable out-of-order flushing if you know that the client’s web browser has JavaScript enabled.

Also, moving DOM nodes may cause the page to be reflowed, which can be visually jarring to the user and result in more client-side CPU usage.

In combination with out-of-order flushing, it may be beneficial to move `<script>` tags that link to external resources to the end of the first chunk (before all of the out-of-order chunks). While the server is busy preparing the rest of the page, the client can start downloading the external JavaScript required to make the page functional.

![out of order flush](https://tech.ebayinc.com/assets/Uploads/Blog/2014/12/out-of-order-flush.png)

https://tech.ebayinc.com/engineering/async-fragments-rediscovering-progressive-html-rendering-with-marko/
