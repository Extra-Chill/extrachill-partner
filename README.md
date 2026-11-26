# Extra Chill Partner

A WordPress plugin for partner venue websites. List your shows once on [Extra Chill](https://extrachill.com) and they show up on your own site:

- **Server-rendered event listings** that search engines can crawl. No iframe and no client-side widget.
- **Schema.org `MusicEvent` JSON-LD** for every event, so your shows can appear in Google's event results.
- **Ticket buttons** that go straight to Extra Chill's hosted checkout.
- An optional **Booking Embed** block for your venue's hosted Extra Chill booking page.

Your API key stays on your server; visitors' browsers never see it. Requires WordPress 6.5+ and PHP 7.4+. No build step and no other plugins needed.

## Install

1. Download `extrachill-partner.zip` from the [latest release](https://github.com/Extra-Chill/extrachill-partner/releases/latest).
2. In WordPress, go to **Plugins → Add New → Upload Plugin**, then upload and activate the zip.
3. Go to **Settings → Extra Chill** and paste your partner API key. Once the key works, the page shows your venue's name.
4. Add the **Upcoming Events** block to a page, or use the shortcode `[extrachill_events limit="10"]`.
5. Optional: add the **Booking Embed** block. Your venue needs booking turned on, and Extra Chill must allow your site's exact HTTPS address.

Don't have a key? Your venue team on Extra Chill can get one. See the guides below.

## Guides

The full Partner Websites guides live at **[docs.extrachill.com/partner-websites](https://docs.extrachill.com/partner-websites)**:

- WordPress plugin setup
- Partner API reference, for custom (non-WordPress) builds
- Custom website builds

## Customizing

- **Styling:** override the `extrachill-partner-*` CSS classes in your theme.
- **Cache time:** the `extrachill_partner_cache_ttl` filter sets how long events are cached, in seconds (default 900). If Extra Chill can't be reached, the last good copy keeps showing.
- **API base:** the `extrachill_partner_api_base` filter changes the API base URL (up to `/partner`, without `/events`).

## Development

```sh
composer install
composer test
```

CI runs Homeboy lint and test on every pull request. Merging to `main` cuts a release automatically: Homeboy reads the [conventional commits](https://www.conventionalcommits.org/) (`fix:` → patch, `feat:` → minor), updates the version and `docs/CHANGELOG.md`, and attaches a versioned `extrachill-partner.zip` to the GitHub Release.

## License

GPL-2.0-or-later. See [LICENSE](LICENSE).
