# Hunt Country Soda Co. website

Static site for huntcountrysodaco.com, hosted free on GitHub Pages with the domain on Cloudflare.

## Files

- `index.html` – the whole site (styles and scripts are inside)
- `assets/` – the can photo, the badge and the horseshoe mark
- `404.html` – page shown for broken links
- `CNAME` – tells GitHub Pages to serve the site at huntcountrysodaco.com
- `.nojekyll` – tells GitHub to publish the files as they are

## 1. Put the files on GitHub

1. Sign in at github.com and click **New repository**.
2. Name it `huntcountrysodaco`, set it to **Public** (free Pages needs a public repo), and click **Create repository**.
3. On the new repo page, click **uploading an existing file**.
4. Drag in everything from this folder, including the `assets` folder, `CNAME` and `.nojekyll`. (On a Mac, press Cmd+Shift+. in Finder to see `.nojekyll`.)
5. Click **Commit changes**.

## 2. Turn on GitHub Pages

1. In the repo, go to **Settings → Pages**.
2. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder **/ (root)**, then **Save**.
3. Under **Custom domain**, confirm it shows `huntcountrysodaco.com` (the CNAME file fills this in). If not, type it and **Save**.

## 3. Point the domain at GitHub (Cloudflare)

In Cloudflare, open the domain, then **DNS → Records**, and add:

| Type  | Name | Content                    | Proxy status |
|-------|------|----------------------------|--------------|
| A     | @    | 185.199.108.153            | DNS only (grey cloud) |
| A     | @    | 185.199.109.153            | DNS only (grey cloud) |
| A     | @    | 185.199.110.153            | DNS only (grey cloud) |
| A     | @    | 185.199.111.153            | DNS only (grey cloud) |
| CNAME | www  | YOUR-GITHUB-USERNAME.github.io | DNS only (grey cloud) |

Delete any older A or CNAME records for `@` or `www` that point elsewhere.

Keep the proxy **off** (grey cloud) so GitHub can issue the security certificate. After the site loads with the padlock, you can turn the orange cloud on if you want; if you do, set Cloudflare **SSL/TLS** mode to **Full**.

## 4. Turn on HTTPS

Back in **Settings → Pages**, wait for the DNS check to pass (minutes to a few hours), then tick **Enforce HTTPS**.

## Before you share the link

- **Prices.** $14 four-pack, $39 twelve-pack and $22 syrup are sample prices. Search `opts:[` in `index.html` to change them.
- **Free delivery threshold.** Search `var FREE=50` to change it.
- **Forms.** Wholesale requests and email sign-ups show an "opens soon" message until you connect a form service. Create a free form at formspree.io, copy its endpoint URL, and paste it between the quotes in `var FORM_ENDPOINT='';` in `index.html`. Submissions then arrive by email.
- **Checkout.** The cart works on the page, but checkout shows "Online checkout opens soon." Selling online needs a store service such as a Shopify Buy Button, Snipcart or Stripe Payment Links.
- **Find us.** Replace "Market days and tasting stops / Posted here soon" with real stops when you have them.

## Making changes later

Edit a file on GitHub (pencil icon) and commit. The live site updates within a minute or two.
