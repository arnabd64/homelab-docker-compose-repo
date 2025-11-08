# Caddy

Caddy is a modern, lightweight web server and reverse proxy designed for simplicity, security, and automation. It automatically manages HTTPS certificates using Let’s Encrypt, which makes it ideal for securely exposing backend services without manual certificate handling. As a reverse proxy, Caddy forwards client requests to backend servers (such as web apps, APIs, or containers) while handling SSL termination, load balancing, and URL routing. Its human-friendly configuration file, **Caddyfile**, allows developers to easily define routing rules, domain mappings, and security settings in just a few lines. Because of its built-in support for automatic HTTPS, simple syntax, and extensibility through plugins, Caddy is often used as a drop-in reverse proxy solution for containerized environments like Docker.

# Domain name for HTTPS

Caddy automatically generates and manages TLS certificates for you on private domains like `.localhost` or `.local` domains. But using these domains means that you have to manually copy the Certificates to your devices to avoid the HTTPS warning in your Browser.

You can get a domain from Cloudflare or any other domain registrar and then manage the DNS using cloudflare in order to use my deployment.

Once you have added your domain to your cloudflare dashboard, Generate the following:

1. `A` record for your root domain (`example.com`) that points to the Local IP of your server (`192.168.0.101`)
2. `CNAME` record for `*.example.com` that points to `example.org`
3. A Cloudflare API key
    1. Go to https://dash.cloudflare.com
    2. *Profile* -> *API Tokens* -> *Create Token*
    3. Create a Custom Token with these Permissions: **Zone:Zone:Read** and **Zone:DNS:Edit**
    4. Don't change any other options and Create the token.
4. In the server's `.bashrc` file add the following lines:
```bash
export CLOUDFLARE_API_TOKEN="paste-your-token"
export CLOUD_EMAIL="cloudflare-email"
```
5. Restart `bash` by running `source ~/.bashrc`
