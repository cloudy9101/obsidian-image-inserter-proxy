# Obsidian Image Inserter Proxy
This is the proxy between the obsidian image inserter plugin and Unsplash API. It needs this proxy as Unsplash API requires not to expose the client ID to users.
The basic here is this proxy receive requests without client ID and send the request to Unsplash API with client ID. It makes sure the client ID won't expose to users.

# Selfhost
This is a simple cloudflare worker [[doc]](https://developers.cloudflare.com/workers/get-started/guide/).

1. Clone the codes.
2. run `npm install`
3. Update wrangler.toml, input your Unsplash API client ID to the [vars] section.
4. run `wrangler dev`, this will start a local server.
```
Listening at http://0.0.0.0:8787
```
5. You can input this local address to Obsidian Image Inserter plugin as proxy address.
6. Test the plugin to make sure it works.
7. run `wrangler publish`, this will publish your codes to cloudflare worker.
8. Find the published worker in cloudflare, and use the worker's url as plugin's proxy address.

# Other Host Options
As the goal of this repo is to provide a proxy server. You can use any technology to do the same task.

- A nginx server
- An AWS lambda function
- Any web server
- etc
