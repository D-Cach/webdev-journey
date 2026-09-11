# How the Web Works

At a high level, the web works because computers agree on a common set of rules for finding each other and exchanging information. Your browser is a client — it makes requests. Somewhere else, a server is waiting to receive those requests and send back a response. In between, there's a naming system (DNS) that translates human-friendly names into machine-friendly addresses, and a transfer protocol (HTTP/HTTPS) that defines the actual format of the request and response.

None of this is magic — it's just a layered handoff: name → address → connection → request → response → rendering. The steps below walk through exactly what happens, in order, from typing a URL to seeing a finished page.

1. **Type the URL, hit Enter.**
   You typed a name (`theodinproject.com`), but computers route traffic using IP addresses, not names. The browser needs to translate one into the other before anything else can happen.

2. **DNS lookup.**
   The browser asks a DNS resolver "what's the IP address behind this name?" and gets back a number — something like `104.21.x.x`. This is basically the internet's phone book lookup.

3. **Open a connection.**
   The browser connects to that IP address on port 443, which is the standard port for HTTPS (encrypted traffic). Think of the IP as the building address and the port as which door to use.

4. **Send an HTTP request.**
   The browser sends a request that includes a method (`GET`, meaning "give me this"), a path (`/`, meaning the homepage), and a bunch of headers with extra context about the request.

5. **Server responds with a redirect.**
   Instead of the page, the server sends back a `301` status (permanent redirect) and a `Location` header pointing to `https://www.theodinproject.com`. The server is saying "that's not the real address, go here instead."

6. **Browser follows the redirect.**
   It repeats steps 2 through 4, but this time targeting the `www` address it was just handed.

7. **Server responds with the actual page.**
   This time it's a `200` status (success), a `content-type` header saying `text/html`, and the actual HTML document in the body.

8. **Browser finds more things it needs.**
   Reading through the HTML, the browser notices references to other files — CSS stylesheets, JavaScript files, images, fonts, etc. (around 62 of them in this case) — and fires off a separate request for each one.

9. **Browser builds and renders the page.**
   It turns the HTML into the DOM (a structured tree representation of the page), applies the CSS for styling, and runs the JavaScript (which might trigger even more network requests for data). Then it calculates layout and paints pixels to the screen.

10. **Page appears.**
    Everything above happens in a fraction of a second, and what you see is the finished, styled, interactive page.