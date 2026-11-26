# WooCommerce VPS: How much RAM does your store need, what does it cost after the first term, and which SixtyNet plans can serve a storefront? (Full plan table + sizing by order volume)

Most WooCommerce stores don't need a VPS yet. Below roughly 100 orders a month, shared hosting handles the cart, checkout and order emails without drama, and moving up early buys you a bigger bill and a few weekends of server work. Past that line, WooCommerce's own baseline is 1 vCPU and 2GB RAM, and the practical floor for a live shop is 4GB.

On SixtyNet, one detail decides everything: only the LAX line can host a public store. The cheaper residential-IP plans block ports 80 and 443, so a shop that customers reach over HTTPS cannot run on them at all. LAX-STARTER (2 vCPU, 2GB RAM, 40GB NVMe, 5TB traffic) is **$200/year**; LAX-MICRO (4 vCPU, 4GB RAM, 80GB NVMe) is **$400/year**, and that's the plan worth buying once you're past 1,000 products or 1,000 orders a month.

> **Quick pick:** LAX-MICRO at $400/year (list $480) is the plan most growing stores should take: 4 vCPU, 4GB RAM, 80GB NVMe at 12,500 IOPS and 10TB of traffic, with DDoS protection included. Take LAX-STARTER at $200/year only if the catalog is small and the order count is still in the low hundreds. 👉 [See SixtyNet's LAX VPS plans and current annual pricing](https://sixtynet.net/aff.php?aff=39)

## Which SixtyNet plans can actually run a WooCommerce store

SixtyNet lists three product lines on one page, and they are not interchangeable. The residential-IP plans and the China Unicom premium plan both carry an explicit notice that ports 80 and 443 stay closed for IP risk control. That notice does not appear on the LAX plans, which are the ones sold with DDoS protection for normal web hosting.

Hardware is the same across the board: KVM virtualization on AMD EPYC CPUs, DDR4 3200MHz memory and NVMe storage, out of a Los Angeles datacenter. The difference is the IP and the network.

### LAX line (the only line to consider for a storefront)

| Plan | vCPU / RAM | Storage | Traffic | Price (annual) | Order |
| --- | --- | --- | --- | --- | --- |
| LAX-STARTER | 2 / 2GB | 40GB NVMe, 12,500 IOPS | 5TB | **$200/yr** (list $240, save 17%) | [Get LAX-STARTER](https://sixtynet.net/aff.php?aff=39) |
| LAX-MICRO | 4 / 4GB | 80GB NVMe, 12,500 IOPS | 10TB | **$400/yr** (list $480, save 17%) | [Get LAX-MICRO](https://sixtynet.net/aff.php?aff=39) |
| LAX-MEDIUM | 8 / 8GB | 160GB NVMe, 25,000 IOPS | 20TB | **$800/yr** (list $960, save 17%) | [Get LAX-MEDIUM](https://sixtynet.net/aff.php?aff=39) |
| LAX-LARGE | 8 / 16GB | 320GB NVMe, 25,000 IOPS | 40TB | **$1,600/yr** (list $1,920, save 17%) | [Get LAX-LARGE](https://sixtynet.net/aff.php?aff=39) |

Every plan in this table includes DDoS protection, 2G to 10G premium network uplink depending on tier, and full root access.

### Residential-IP line (not for a shop)

These plans exist for social media management, scraping and other work where a home-looking IP matters. The page states plainly that ports 80 and 443 are closed. A WooCommerce store behind that restriction is unreachable to customers.

- 2 vCPU / 2GB / 40GB NVMe / 5TB traffic
- 4 vCPU / 4GB / 80GB NVMe / 10TB traffic
- Residential-MEDIUM: 8 vCPU / 8GB / 160GB NVMe / 20TB traffic, **$860/yr** (list $1,020, save 16%)
- 16 vCPU / 16GB / 320GB NVMe / 40TB traffic

A China Unicom Premium variant at **$2,500/yr** (list $3,000) adds AS9929 routing, free BGP session setup and 95th-percentile billing on a 100M base network. It's built for bandwidth-heavy network work, still residential-IP, still ports closed.

The other thing to note on this line: at least one residential product states that refunds are issued as website balance only. Read your plan's terms before paying.

## Sizing by catalog size and order volume

WooCommerce's stated minimum is 1 vCPU and 2GB RAM. That gets the software running. It doesn't get a store through a sale.

The thresholds that matter, in ascending order:

- **Under about 100 orders a month:** shared hosting is enough. A VPS adds cost and admin work with no customer-visible benefit.
- **New store, catalog up to about 500 products:** LAX-STARTER. 2 vCPU and 2GB covers a fresh shop with a handful of plugins.
- **1,000+ products or 1,000+ orders a month:** 4GB is the working floor. This is LAX-MICRO territory.
- **5,000+ products, or the admin area starts dragging:** step up to 8GB. LAX-MEDIUM doubles both IOPS and traffic here, which matters for database-heavy checkouts.
- **Catalogs near 100,000 products with their own search engine:** 16GB and up. LAX-LARGE.

Two constraints on the entry plan are easy to miss. **40GB of NVMe fills up fast** once you're uploading product photography at full resolution, and the 12,500 IOPS rating on the starter and micro tiers is half what the medium and large plans get. For a 300-SKU store neither matters. For a 3,000-SKU store with a big media library, both do. 👉 [Check the LAX-MICRO plan if your catalog is past 1,000 products](https://sixtynet.net/aff.php?aff=39)

## What the yearly price really means

SixtyNet bills these plans annually, and the "save 17%" is the discount against the monthly rate. That makes the cash outlay predictable in a way most budget hosts' pricing isn't, but it also means $200 to $1,600 leaves your account in one go.

Compare that to how the low end of this market prices things. Hostinger's KVM 1 shows $6.49/month, which requires paying $155.76 upfront for 24 months, then renews at **$11.99/month** for the same term. GreenGeeks lists its 4GB VPS at $9.99/month as a promotional rate against a $19.99 list price, and renews at **$19.99/month**. In both cases the advertised number is a first-term figure, and the second-term figure is roughly double.

SixtyNet's page shows an annual price next to a struck-through higher annual figure. What it does not state is what you'll be charged when that year renews. Ask support before you buy, in writing, and keep the answer. 👉 [Compare SixtyNet's annual pricing against the monthly rate](https://sixtynet.net/aff.php?aff=39)

The other half of the cost equation is what you're not paying. WooCommerce core takes no platform fee and no revenue share. Shopify runs $39 to $399/month, or $29 to $359/month billed yearly, and charges 2%, 1%, 0.6% or 0.2% if you use a third-party payment provider. At $10,000 in monthly sales on the Basic tier, that cut is about $200 a month. Payment processing is separate either way: WooPayments charges 2.9% + $0.30 on US cards, and Stripe, PayPal and Square all work with WooCommerce.

Put together, a $400/year VPS plus a $30/month extension budget is cheaper than Shopify at almost any volume. The trade is that you run the server.

## What self-managed actually asks of you

Root access means the operating system, PHP, MariaDB, WooCommerce, your theme and every plugin are yours to maintain, including update conflicts and server tuning like PHP-FPM worker counts and `innodb_buffer_pool_size`. The host covers hardware, network and virtualization. That division is standard across self-managed VPS products.

The short list of things a WooCommerce store needs on a fresh server:

- **PHP 8.3 or 8.4 and MariaDB 10.6+.** WooCommerce 10.8 and later recommends WordPress 6.9+, PHP 8.3+, MySQL 8.0+ or MariaDB 10.6+, HTTPS, and a 256MB WordPress memory limit. `WooCommerce > Status > System Status` lists anything missing after install.
- **Redis.** WooCommerce's hosting guidance treats a persistent object cache as part of the baseline spec. It keeps prices, SKUs and stock levels in memory so the database isn't running the same query on every request. Budget about **128MB for a small store and 512MB for a busy one**. Redis is not a page cache, and on small servers some owners report CPU load rising after enabling it, so watch the hit rate.
- **A real cron job.** WP-Cron only fires when someone loads a page. Action Scheduler depends on it to send order emails, apply scheduled sale prices and run subscription renewals, which means those jobs run late on a quiet store and add overhead to every page view on a busy one. Add `define('DISABLE_WP_CRON', true);` to `wp-config.php` and run `wp cron event run --due-now` from a system cron every one to five minutes.
- **Backups you actually own.** On a self-managed VPS, backups are your problem, and orders change all day. Run `wp db export` from cron several times a day, then copy the dumps and files off the server to Google Drive or S3. What you need: the database (including the `actionscheduler_` tables), `wp-content` for product images and downloads, and `wp-config.php`. The Redis cache rebuilds itself and doesn't need backing up.

If that list reads like a weekend you'd rather not spend, a managed WooCommerce host is the honest answer, and SixtyNet isn't it.

## The 800ms checkout test

Cart, checkout and My Account pages can't be served from a page cache, because each one shows a specific shopper's cart. Every request runs PHP and hits the database. WooCommerce treats a checkout that takes more than **800ms** as a sign the store has outgrown its host.

That's your upgrade trigger, and it's measurable. Install a test order, time the checkout, and check `WooCommerce > Status > System Status` after every PHP or plugin change. If a 4 vCPU / 4GB plan is pushing 800ms with a normal plugin load, more RAM won't fix it; the database queries will.

One free win first: **HPOS**. Since WooCommerce 8.2, new stores can keep orders in four dedicated tables instead of `wp_posts`. WooCommerce reports order creation up to 5x faster and checkout up to 1.5x faster. Existing stores switch under `WooCommerce > Settings > Advanced > Features`, and compatibility mode keeps both table sets in sync during the transition. On SixtyNet's 12,500 IOPS starter tier, that's the difference between a checkout that feels instant and one that doesn't.

## Migrating without losing orders

The WordPress XML export won't move a store. It leaves out orders, products and WooCommerce settings.

The working sequence: dump the database and copy `wp-content`, update `wp-config.php` with the new database credentials on the VPS, install and test the store against the new server's IP, place a test order, then repoint the domain. Keep the old host live until the test order completes and emails arrive.

## How SixtyNet compares on paper

All figures below are the entry plan each provider lists for WooCommerce-capable VPS hosting, as shown on their pages.

| Provider | Entry plan | Verified price | What to know |
| --- | --- | --- | --- |
| SixtyNet | LAX-STARTER: 2 vCPU, 2GB, 40GB NVMe, 5TB | $200/yr | LA datacenter, DDoS included; residential line blocks ports 80/443 |
| GreenGeeks | 4GB: 2 vCPU, 4GB, 80GB NVMe, unmetered | $9.99/mo promo, renews $19.99/mo | 30-day refund; 8GB tier for 1,000+ products or orders |
| Hostinger | KVM 1: 1 vCPU, 4GB, 50GB NVMe, 4TB | $6.49/mo on a 24-month term ($155.76 upfront), renews $11.99/mo | Cheapest per gigabyte; renewal nearly doubles |
| Bluehost | NVMe 4 / 8 / 16 | $9.49 / $12.99 / $25.99 | Term and renewal price not stated on the page |
| LightNode | Start: 2 vCPU, 4GB, 50GB NVMe, 1TB | $13.7/mo | WooCommerce preinstalled on Ubuntu 24.04; setup over SSH tunnel |
| Liquid Web | General: 2 vCPU, 2GB, 40GB SSD, 10TB | $33/mo | Figures from a 2024 page; likely changed since |

Per gigabyte of RAM, SixtyNet is the most expensive option here. What you're paying for is a Los Angeles location with premium routing toward Asia, DDoS protection bundled in, and annual billing that doesn't disguise a renewal cliff. If your customers are mostly in Europe and your budget is the deciding factor, Hostinger or GreenGeeks will cost less. If your buyers are in the US West or East Asia, the network path is worth something.

## FAQ

**How many orders a month before a VPS makes sense?**
Around 100. Below that, shared hosting handles WooCommerce's database queries without a visible slowdown, and the VPS adds maintenance work rather than revenue.

**Is 2GB of RAM enough for WooCommerce?**
It meets the stated minimum and runs a new store. For anything live, 4GB is the working floor. On SixtyNet's starter tier, the tighter constraint is the 40GB disk, not the RAM.

**Do I need Redis?**
WooCommerce runs without it, but its own hosting guidance lists a persistent object cache as part of the baseline. Enable it, then watch the cache hit rate and CPU load for a week.

**Will the price go up when the year renews?**
SixtyNet's pricing page shows a discounted annual rate against a higher list rate but doesn't publish renewal terms. Get the renewal number from support before you pay.

**What's the refund window?**
A 3-day money-back guarantee is mentioned in third-party write-ups of SixtyNet, and at least one residential product's refund is issued as account credit only. Confirm the terms for the specific plan you're buying; this is not the 30-day window GreenGeeks offers.

**Can one VPS run several stores?**
Yes, and agencies commonly do it. On SixtyNet, LAX-MEDIUM and LAX-LARGE with 8 vCPU and 8 to 16GB have room for a few small stores, provided none of them is running a flash sale at the same time.

## Before you order

Match the plan to the catalog, not to the traffic you hope for:

- **New store, under 500 products, under 1,000 orders a month** → LAX-STARTER at $200/year.
- **1,000+ products or 1,000+ orders a month** → LAX-MICRO at $400/year. This is where most stores land.
- **5,000+ products, or the admin panel already feels slow** → LAX-MEDIUM at $800/year.
- **Six-figure SKU count, a dedicated search engine, or several stores on one box** → LAX-LARGE at $1,600/year.

Two things to settle before you pay: **what the renewal price will be**, and **whether backups or snapshots are included**. The pricing page doesn't answer either, and both change the real cost of year two.

If the answer on both is acceptable and your customers are in the US or Asia, the LAX line is a straightforward buy. 👉 [Pick your SixtyNet LAX plan](https://sixtynet.net/aff.php?aff=39)
