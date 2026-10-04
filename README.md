# residential proxy cost: how per-GB and per-IP pricing works, what you actually pay at each volume, and how to avoid overbuying

Two people can both hand a proxy provider $300 a month and get wildly different amounts of work done. One runs 12,000 lightweight SERP checks a day and never comes close to the limit. The other spins up a headless browser, pulls images and fonts and analytics scripts along with every page, and burns through the same money in nine days.

The sticker price isn't the cost. The cost is the sticker price multiplied by the shape of your traffic.

That's the whole problem with searching for residential proxy cost: every provider publishes a number, almost none of them publish a number you can compare against anyone else's. Here's how to actually read those numbers, what the market charges right now, and how a provider like 9Proxy structures its plans so you can work out whether you're paying $24 or $2,300 for the thing you need.

## Why per-GB and per-IP prices can't be compared

Residential proxies are billed in three units, and they're not variations of each other. They're different products wearing the same label.

- **Per GB**: you buy traffic. IPs are unlimited, generated on demand, rotated or held sticky. You pay for what flows through them.
- **Per IP**: you buy addresses. Bandwidth through each one is usually unlimited, but you get a fixed number of them, and they behave like real consumer connections, which means they come and go.
- **Per request**: you buy calls to an endpoint. This shows up mostly in managed scraping APIs rather than raw proxy access.

A supplier quoting $0.68/GB and a supplier quoting $0.24/IP are not offering cheaper and more expensive versions of the same thing. One is selling data, the other is selling identity.

The practical version of this, which one proxy-pricing breakdown puts in useful numbers: 600 GB a month spread across hundreds of addresses costs roughly the same under either model. The same 600 GB pushed through just ten addresses is where per-IP pricing wins by an order of magnitude, because ten addresses at $1.25 each is $12.50 with all the traffic included [1].

So the first question isn't "which provider is cheapest." It's "how many addresses does my workload actually need, and how much data does each one move?"

## What residential proxies cost right now

Residential traffic comes from real consumer connections, and the provider has to pay for that access. That's why it costs many times more per gigabyte than datacenter, and why the market floor sits where it does.

| Segment | Per-GB range | Who's there |
| --- | --- | --- |
| Budget | $0.65–$1.50/GB at entry | DataImpulse (from ~$1/GB), Rapidproxy (from $0.65/GB), 9Proxy (from $0.68/GB at volume) |
| Mid-market | $0.79–$3.75/GB | GeoNode (from $0.79/GB, dropping to $0.27/GB above 1 TB), Decodo ($3.75/GB at 3 GB, $2.75/GB at 100 GB) |
| Premium | $4–$8.40/GB | IPRoyal ($7.99 first GB, then $5.15/GB), Bright Data (from $8.40/GB) |

Per-IP pricing runs on a different axis: GeoNode lists ISP proxies from $1.25/IP, Rapidproxy lists static residential from $5/IP/month, and 9Proxy's IP-based residential drops as low as $0.018/IP at the 500,000-IP tier.

An unusually cheap residential offer is worth a second look rather than a purchase. If a provider is well under the market floor, either they have a volume advantage they can explain, or the pool was assembled in a way that didn't involve paying anyone, which tends to show up later as instability.

## The costs that never appear on the pricing page

Budgets break here more often than they break on the headline rate.

**Retries are billable.** A 20% failure rate means you pay for 20% more traffic than you get useful data out of. On hardened targets the failure rate is far higher, and every failed request still transfers bytes.

**Rendering dominates bandwidth.** A headless browser fetching a product page pulls images, fonts, video preloads and third-party scripts. Blocking the resource types you don't need can cut bandwidth by 70–90%, which is the single largest lever available on a metered plan.

**Failed requests aren't free.** Blocked responses, redirects, error pages and CAPTCHA challenges all move data across the wire. You pay for the challenge you didn't solve.

**Traffic expiry is a real line item.** Plenty of providers void unused bandwidth at the end of each month. If your usage is seasonal or project-based, you're buying capacity you'll never burn.

**Minimum commitments hide the real rate.** The attractive per-GB price often requires a volume tier you have to reach. Check what you pay at your volume, not at the volume that unlocks the headline number.

**Engineering time is the biggest one.** Building and maintaining a scraping pipeline is ongoing work, not a one-time setup cost. It rarely makes it into a spreadsheet, and it's frequently larger than the proxy bill.

That expiry point is where 9Proxy's structure is genuinely different from a monthly subscription. Its GB-based plans carry a 180-day validity window, and Enterprise GB packages have no expiry at all. You buy 200 GB, you have six months to use it. For anyone running campaigns in bursts rather than at a constant rate, that changes the effective cost per useful gigabyte quite a bit.

👉 Check how 9Proxy's GB validity and plan tiers compare to what you're paying now

## 9Proxy's actual plans and prices

9Proxy sells residential access two ways, plus bundles that mix them. The company's 20M+ IP pool spans 90+ locations with targeting down to country, state, city, ZIP code and ISP, over HTTP/HTTPS and SOCKS5. It updated IP-based and bundle pricing on June 1, 2026; GB-based prices were left alone.

The IP-based model is built for session stability: you get a fixed number of addresses, bandwidth through them is unlimited while they're active, and unused IPs don't expire. Each individual IP stays live from a few hours up to roughly 24 hours, because that's how ordinary residential connections behave. Authentication runs through the 9Proxy desktop app with local port forwarding.

| IP package | Price per IP | Total | Notes |
| --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | Smallest entry point |
| 500 IPs | $0.144 | $72 |  |
| 1,000 IPs | $0.084 | $126 | Includes 500 bonus IPs |
| 2,500 IPs | $0.084 | $210 |  |
| 5,000 IPs | $0.072 | $360 |  |
| 15,000 IPs | $0.048 | $720 |  |
| 25,000 IPs | $0.035 | $863 |  |
| 50,000 IPs | $0.029 | $1,438 |  |
| 100,000 IPs | $0.023 | $2,300 | Business tier |
| 200,000 IPs | $0.021 | $4,140 | Business tier |
| 500,000 IPs | $0.018 | $8,625 | Lowest per-IP rate |

👉 Get 9Proxy's IP-based package pricing

The GB-based model works the other way round: no per-IP activation cost, unlimited endpoints you can generate yourself, and both rotating and sticky session modes. Targeting and proxy generation both happen in the dashboard, and you authenticate with username/password or by whitelisting your IP, so no desktop app is required. This is the one built for cloud jobs and automation.

| GB package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days |
| 50 GB (+5 GB bonus) | $2.10 | $105 | 180 days |
| 100 GB | $1.50 | $150 | 180 days |
| 200 GB | $1.00 | $200 | 180 days |
| 1,000 GB | $0.80 | $800 | 180 days |
| 2,000 GB | $0.75 | $1,500 | 180 days |
| 3,000 GB (Enterprise) | $0.72 | $2,160 | No expiry |
| 6,000 GB (Enterprise) | $0.70 | $4,200 | No expiry |
| 10,000 GB (Enterprise) | $0.68 | from $6,800 | No expiry |

👉 Compare 9Proxy's GB-based packages

Enterprise adds team mode (one owner plus up to five members), shared bandwidth with per-member traffic controls, full activity logs, and unlimited share code creation. If you're running several clients out of one account, that's the tier where the admin overhead drops.

Bundles exist for workloads that need both a stable set of addresses and metered rotation in the same month.

| Bundle | What's included | Price |
| --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 |
| Popular | 1,500 IPs + 50 GB | $180 |
| Pro | 5,000 IPs + 500 GB | $720 |

👉 See 9Proxy's current bundle pricing

## Working out which model fits your workload

Forget the rate tables for a minute. Answer these three questions and the model picks itself.

**How much data does a typical request move?** If you're pulling JSON APIs or lightweight HTML, per-GB is almost always cheaper. If you're rendering full pages with a browser, a single request can consume a megabyte or more, and metered billing gets expensive fast.

**Do you need the same address twice?** Account login flows, shopping carts, region-locked dashboards and platforms with aggressive bot detection all want a consistent identity. Per-GB pricing can give you sticky sessions, but per-IP gives you a fixed address you own for as long as it lives.

**Is your usage flat or bursty?** Flat monthly usage suits a subscription. Bursty, project-based usage suits a balance model where unused credit doesn't evaporate at month end, which is what the 180-day window is for.

Three concrete shapes:

- **Solo SEO operator running rank tracking.** 50,000 SERP checks a day at roughly 200 KB each lands near 300 GB a month. Residential at scale-tier per-GB pricing gets you hundreds of dollars; datacenter handles most of it far cheaper. Only reach for residential on the engines that actually block datacenter ranges.
- **E-commerce price monitoring against hardened sites.** 10,000 checks a day at 2 MB average is about 600 GB a month. At 9Proxy's 1,000 GB tier that's $800, and 9Proxy's unlimited-bandwidth IP model is worth pricing against it if you can work with a few hundred stable addresses instead of thousands of rotating ones.
- **Managing 30 social accounts.** You barely need bandwidth. You need 30 addresses that stay put. Per-IP pricing at the 100-IP tier is $24, and buying GB packages for this job would be paying for a resource you aren't using.

That last comparison is the point. The same provider sells you a $24 plan and an $8,625 plan because those are answers to genuinely different problems.

## Before you pay, check the fine print

- **Where does the traffic expire, and how fast?** A cheap per-GB rate with a 30-day clock is more expensive than a slightly higher rate with 180 days, if you don't burn it evenly.
- **How is bandwidth measured?** Some providers round up at the megabyte, some bill for protocol overhead, some have a super proxy path that doesn't count toward your total. Those details move the bill.
- **What's the minimum commitment?** Balance-based models let you start with 5 GB for $15. Monthly subscriptions don't.
- **Does the low rate require you to buy 500,000 IPs?** Volume discounts are genuine, but they only help if you're actually using the volume.
- **How is the pool sourced?** Ask. A provider willing to answer that question is telling you something about how the network will behave in six months.
- **What's the trial situation?** 9Proxy offers a limited trial for new users subject to availability, which is enough to run your own target against the pool before committing to a larger package.

Most people overpay for the first month because they forecast the workload they imagine having rather than the one they have. Buy the smallest plan that covers your current usage. The upgrade path from 100 IPs to 500 IPs is one click, and dropping the per-unit rate from $0.24 to $0.144 is a $48 saving once you've measured that you need it.

👉 Start with 9Proxy's smallest package and measure your actual burn rate

## Short answers to the questions people actually type

**Is $1/GB cheap for residential proxies?** Yes. It's around the market floor for entry-level GB packages, and it generally requires either a budget-tier provider or a volume tier to reach.

**Why do I get quoted per IP when I asked about per GB?** Because your described workload needs stable identities rather than volume. Push back on it if you're doing high-rotation scraping, and take it seriously if you're running accounts.

**Does unlimited bandwidth per IP really mean unlimited?** It means unlimited while the IP is active, which for residential connections is measured in hours, not months. Budget for the numbers of addresses you need, not one address running forever.

**What's the cheapest thing I can buy to test a provider?** A small GB package. 9Proxy's 5 GB tier is $15 with a 180-day window, and it's enough to run a real target through the pool rather than a demo request.

**Do I need both models?** Only if your workload genuinely has two halves, which is what the bundles are for. If everything you run wants stable addresses, buy IPs and ignore the GB side entirely.
