# What is the difference between script, script async and script defer?

- `script` HTML parsing is blocked, the script is fetched and executed immediately;
- `script async` HTML parsing isn't blocked, the script will be fetched and executed in parallel
- `script defer` HTML parsing isn't blocked, the script will be executed after the page has finished parsing

The order of execution `async` scripts is not guaranteed.

If there are multiple `defer` scripts, they will be executed in the order they were encountered in the document.

https://www.growingwiththeweb.com/2014/02/async-vs-defer-attributes.html
