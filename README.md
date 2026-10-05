# proxy providers: how to compare per-GB pricing, expiring traffic and targeting fees before you lock in

Most people typing "proxy providers" into a search box are in one of two situations. Either they're buying proxies for the first time and have no idea why one provider wants $1 per gigabyte while another wants $8, or they already have a provider and suspect they're paying for traffic that quietly evaporates at the end of every month.

The listicles in the top results don't usually answer either question. They rank eight vendors, quote a starting price, and move on. What they skip is the part that actually decides your invoice: how the provider bills, what it counts, and what happens to your unused balance.

So let's do that part first, then get specific about where one provider — DataImpulse — sits in that picture.

## Pick the proxy type before you even look at the vendor list

Prices that look absurd next to each other are often just different products. A $0.50/GB datacenter rate and a $5/GB premium residential rate aren't competing offers; they're different networks for different jobs.

| Proxy type | Where the IP comes from | How it's usually billed | Typical fit |
| --- | --- | --- | --- |
| Datacenter | Hosting and cloud networks | Per GB, or per IP/month | High-volume work on targets with light defences |
| Residential (rotating) | Consumer ISP connections | Per GB | Geo-sensitive pages, e-commerce, SERPs, social |
| ISP / static residential | ISP-registered, hosted on servers | Per IP/month | Long sessions where the address must stay put |
| Mobile (3G/4G/5G/LTE) | Carrier networks | Per GB, per port, or per day | Mobile-specific experiences, the most defensive targets |

CNET's 2026 roundup makes the useful point that proxying is really about *whether your request gets through*, not about how big the advertised pool is. IPs scoring badly on fraud checks get blocked regardless of which logo is on the invoice. Residential and mobile pools matter more than datacenter depth for that reason, which is why they cost more.

Two practical rules fall out of this.

First, don't buy residential traffic for pages that datacenter egress renders fine. That's the single most common way people overspend.

Second, don't buy mobile traffic just because a target is hard. Scrapeless's 2026 guide puts it plainly: mobile routing adds cost and complexity, and if the page behaves identically through residential IPs, you've paid a premium for nothing.

## The four billing models don't convert into each other

Here's why provider comparisons feel slippery. Four different units are in play:

- **Per GB** — bandwidth-based. Standard for residential, datacenter and mobile.
- **Per IP/month** — used for ISP, static residential and dedicated datacenter.
- **Per request, or per 1,000 results** — managed scraper and SERP APIs.
- **Subscription vs pay-as-you-go** — a layer on top of all three.

A $/GB figure and a $/1,000-requests figure measure different things. You can't rank them on one axis. The number that settles the argument is **cost per successful request**, and you get there with arithmetic:

1,000,000 pages a month at roughly 0.5 MB each is about 500 GB. At $1/GB that's $500. At $5/GB it's $2,500. Then divide by your success rate — at 95%, the $500 case is really about $526 for a million *usable* pages. If you're driving a headless browser that pulls images, fonts and scripts, the byte count goes up before you've collected anything.

This is the number that exposes cheap pools. A $0.50/GB network that blocks half your requests costs more per usable record than a $1/GB network that mostly gets through. Decodo's own 2026 comparison makes this point about DataImpulse directly, and it's the sharpest thing in their write-up: DataImpulse wins on price, and if a meaningful share of requests fail, that advantage narrows fast.

On the market ranges, current published numbers cluster like this: residential runs from around $1/GB at the budget end (PacketStream, Webshare at roughly $1.40/GB, DataImpulse at $1/GB) up to $2.50–$3.60/GB from the mid-market names and $8/GB for Bright Data's pay-as-you-go residential. Datacenter sits well below most of that. Mobile sits well above it.

## Three costs that never make it into the headline price

**Expiring traffic.** You buy 100 GB, use 60, and the other 40 disappear. Repeating that monthly is the most expensive habit in this market, and it's invisible in a comparison table because the advertised rate is identical either way. Non-expiring balances are worth paying a small premium for — sometimes they mean you're paying less overall.

**Minimum top-ups.** A low per-GB rate paired with a $500 monthly minimum isn't a cheap provider; it's an expensive one with good marketing. Check the entry bar before you check the rate.

**Targeting surcharges.** Country selection is usually included. City, state, ZIP and ASN targeting often isn't. If your work is city-level, a country-level quote will materially underestimate your bill. Check this before you build your cost model, not after.

## How to judge a pool without trusting the number on the homepage

You can't validate a residential network from your desk. But you can do better than believing the press release:

**Check the fraud scores, not the pool size.** CNET's methodology leans on IPQualityScore data from Proxyway's market research: the share of IPs scoring *below* 75 is what predicts whether your requests survive. A 90-million-IP pool with dirty addresses is worse than a 10-million-IP pool with clean ones.

**Look for published per-country counts.** Some providers let you see how many addresses exist per country before you pay. That turns "195 countries" from a marketing line into something you can verify against your own target list. DataImpulse does this, and it's a genuinely useful feature if you're geo-specific.

**Separate first-party pools from resold ones.** If a provider is reselling someone else's network, heavy users on that network degrade everyone else's experience. Providers that own their pool tend to say so explicitly, and it's worth checking they do.

**Ignore success rates you can't trace.** An 89% figure from the vendor means little. An 89% figure from someone who ran a fixed page set across a month means a lot. ProxyLook's independent data, for example, records DataImpulse at a 99.3% success rate and around 890 ms average response — close to, but not identical to, the 99.51% DataImpulse publishes itself. That gap is normal and not alarming; the point is to prefer numbers you can at least see the method behind.

## Where DataImpulse actually fits

DataImpulse is a Vilnius-based provider that has been selling since around 2023. Its shape is simple: one pay-as-you-go balance per proxy type, traffic that doesn't expire, no subscription, no monthly commitment. The residential pool is 90M+ addresses across 195 countries, sourced first-party rather than resold, and the company holds ISO certification and markets GDPR compliance.

The pricing ladder is unusually flat, which is either reassuring or annoying depending on how you buy. Residential stays at $1/GB all the way up to 850 GB and only drops to $0.80/GB at 1 TB. There's no reward for buying 200 GB instead of paying as you go.

| Plan | Proxy type | Price | What the entry purchase gets you | Volume step | Billing |
| --- | --- | --- | --- | --- | --- |
| Residential — Intro / Basic | Rotating residential, 90M+ IPs, 195 countries | $1/GB | $5 = 5 GB | — | Pay-as-you-go, traffic never expires |
| Residential — Advanced | Same pool, bulk rate | $0.80/GB | Applies at 1 TB (e.g. $800/TB) | $0.80/GB from 1 TB | Pay-as-you-go, traffic never expires |
| Datacenter | Rotating datacenter, 195+ countries | $0.50/GB | $5 = 10 GB | $0.45/GB from 1 TB | Pay-as-you-go, traffic never expires |
| Mobile | 3G/4G/5G/LTE carrier IPs | $2/GB | $5 = 2.5 GB | $1.60/GB from 1 TB | Pay-as-you-go, traffic never expires |
| Premium Residential | High-speed residential pool, dedicated account manager | $5/GB | $5 = 1 GB ($50 = 10 GB) | Custom pricing from 5 TB | Pay-as-you-go, traffic never expires |
| Custom | Any network type | Negotiated | From 5 TB of traffic | — | Pay-as-you-go |

👉 [Check current DataImpulse plans and top up from $5](https://bit.ly/dataimPulse)

A few details that matter more than the rate card:

Country targeting is included. City, state, ZIP and ASN targeting are paid add-ons — so a city-level campaign at $1/GB is not really a $1/GB campaign, and that's the number to check before you commit. Both rotating and sticky sessions are supported, with sticky sessions lasting 1 to 120 minutes (default 30, bound to ports in the 10000–20000 range). Protocols are HTTP, HTTPS and SOCKS5. You can run up to 2,000 concurrent threads, scalable on request.

There's no free trial. The minimum first purchase is $5, and one independent review site notes the minimum rises to $50 from your second top-up onward — worth confirming at checkout, since it changes how the product suits occasional small jobs. Unused traffic doesn't expire, which softens that considerably: a quiet month isn't a lost month. Intro plans carry a roughly 7-day money-back window for card payments, generally conditioned on not having burned through most of the traffic.

👉 [Compare DataImpulse's per-GB rates across all four proxy types](https://bit.ly/dataimPulse)

TechRadar's review puts the datacenter pool at around 20 million addresses and the mobile pool at around 16 million across 195 locations, with datacenter response times under 100 ms and 99.9% advertised uptime. On the customer side, DataImpulse sits at 4.8/5 on G2.

## What DataImpulse is not for

This matters more than the pitch. DataImpulse publishes its own limits, which is refreshing:

- **No static ISP or static residential proxies.** If you're managing accounts long-term and need the same address across sessions, this is the wrong provider. It's also why multi-accounting isn't a good fit.
- **No managed scraping API.** You write the scraper, handle retries, parse the HTML, and deal with CAPTCHAs yourself. The service provides network egress, nothing above it.
- **No dedicated mobile ports with unlimited bandwidth.** Mobile access is traffic-metered, which isn't a substitute if your workflow needs a private port.
- **Not ideal for banking or government sites.** Public data collection is the stated scope.
- **No PayPal.** Payment is via card, crypto or AliPay according to one review site's listing.

Decodo's summary of the trade-off is fair and worth repeating: one of the lowest per-GB prices on the market, non-expiring pay-as-you-go balance, no free trial, thinner tooling, and weaker performance than premium providers on the most heavily protected targets.

## A shortlist process that takes an afternoon

1. **Name your proxy type per workload.** Most teams need two: datacenter for open pages, residential for the defended ones.
2. **Estimate monthly gigabytes honestly.** Count browser-rendered pages separately — they cost more.
3. **Convert every quote to cost per successful request.** Include targeting surcharges.
4. **Check the entry bar and the expiry rule.** These two decide more than the rate.
5. **Run the same test set across two or three providers.** Same client, same headers, same concurrency, same URL list. Record bytes, status codes and whether the extracted content actually matched.
6. **Keep the raw logs.** A provider that wins overall may lose badly on your specific target mix.

If price is the constraint and your targets sit in the moderately-protected range — marketplace listings, SERPs, price monitoring, ad verification — starting with a $5 balance and measuring your own numbers is a low-risk way to find out. That's exactly what the small entry tier is for.

👉 [Start with a $5 DataImpulse balance and measure your own cost per request](https://bit.ly/dataimPulse)

## Quick answers

**What's a fair price for residential traffic?** Somewhere around $1/GB at the budget end, $3–4/GB mid-market, $5–8/GB at the enterprise tier. Judge it after dividing by your success rate.

**Is cheaper always worse?** No. The right metric is cost per usable record. But a suspiciously low rate with expiring traffic, a high minimum, or a resold pool usually ends up more expensive.

**Per GB or per IP?** Per GB when you need many addresses with light transfer per address. Per IP when you need few stable addresses with heavy transfer.

**Do I need a subscription?** Only if your usage is steady enough to consume the whole allowance. If it fluctuates, pay-as-you-go with non-expiring traffic wastes less.

**Can one provider cover everything?** Rarely. DataImpulse's own documentation points out it doesn't sell static ISP or managed scraping APIs — so teams doing both rotating collection and long-session account work will end up with two vendors.
