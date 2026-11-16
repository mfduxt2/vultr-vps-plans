# Unmanaged VPS hosting: which Vultr plan fits your workload, what the $300 credit requires, and who should skip it (full plan and price table)

Vultr's unmanaged VPS hosting starts at $5/mo for 1 vCPU, 1 GB RAM and 25 GB SSD, or $6/mo if you want NVMe storage. The $300 offer is promotional credit tied to the code `FLY300VULTR`, and the terms printed on Vultr's own coupon page are narrow: new customers only, select products only, cannot be combined with any other offer, restrictions apply.

That's the short version. What follows is every plan in the shared-CPU lineup with current monthly pricing, the parts of the unmanaged/managed split that hosts tend to leave out of their marketing pages, and the specific workloads where paying for a bigger Vultr box is wasted money.

> **Quick pick:** a lab box, a side project or one small site on nginx plus SQLite runs fine on High Performance 1 GB at $6/mo. A real site with MySQL or Postgres, Redis and a deploy pipeline belongs on High Performance 2 GB at $12/mo, and Docker with several containers on one host justifies the 4 GB at $24/mo. 👉 [Check current Vultr plan pricing and spin one up](https://bit.ly/VuLtr)

## All Vultr shared-CPU plans and prices

Prices below are the monthly rates Vultr lists for each plan, billed month to month. Storage is SSD on the Cloud Compute tier and NVMe on High Frequency and High Performance.

| Family | Plan | vCPU / RAM | Storage | Price/mo | Link |
| --- | --- | --- | --- | --- | --- |
| Cloud Compute | Regular 1 GB | 1 / 1 GB | 25 GB SSD | $5 | [View plan](https://bit.ly/VuLtr) |
| Cloud Compute | Regular 2 GB | 1 / 2 GB | 55 GB SSD | $10 | [View plan](https://bit.ly/VuLtr) |
| Cloud Compute | Regular 4 GB | 2 / 4 GB | 80 GB SSD | $20 | [View plan](https://bit.ly/VuLtr) |
| Cloud Compute | Regular 8 GB | 4 / 8 GB | 160 GB SSD | $40 | [View plan](https://bit.ly/VuLtr) |
| Cloud Compute | Regular 16 GB | 6 / 16 GB | 320 GB SSD | $80 | [View plan](https://bit.ly/VuLtr) |
| High Performance | HP 1 GB | 1 / 1 GB | 25 GB NVMe | $6 | [View plan](https://bit.ly/VuLtr) |
| High Performance | HP 2 GB | 1 / 2 GB | 50 GB NVMe | $12 | [View plan](https://bit.ly/VuLtr) |
| High Performance | HP 4 GB | 2 / 4 GB | 100 GB NVMe | $24 | [View plan](https://bit.ly/VuLtr) |
| High Performance | HP 8 GB | 4 / 8 GB | 180 GB NVMe | $48 | [View plan](https://bit.ly/VuLtr) |
| High Performance | HP 16 GB | 8 / 16 GB | 350 GB NVMe | $96 | [View plan](https://bit.ly/VuLtr) |
| High Frequency | HF 1 GB | 1 / 1 GB | 32 GB NVMe | $6 | [View plan](https://bit.ly/VuLtr) |
| High Frequency | HF 2 GB | 1 / 2 GB | 64 GB NVMe | $12 | [View plan](https://bit.ly/VuLtr) |
| High Frequency | HF 4 GB | 2 / 4 GB | 128 GB NVMe | $24 | [View plan](https://bit.ly/VuLtr) |
| High Frequency | HF 8 GB | 3 / 8 GB | 256 GB NVMe | $48 | [View plan](https://bit.ly/VuLtr) |
| High Frequency | HF 16 GB | 4 / 16 GB | 384 GB NVMe | $96 | [View plan](https://bit.ly/VuLtr) |

Three things the table doesn't show. Vultr also sells dedicated-CPU and optimized instances above this range, and the shared lineup caps out at 24 GB RAM / 12 vCPU at roughly $216/mo. Prices are identical across most of the 32 locations listed below, with São Paulo running about 50% higher for the same plan. And the difference between Regular and High Performance isn't just the disk: the regular tier runs on older Intel hardware, while High Performance uses current-gen AMD EPYC or Intel Xeon with NVMe.

## What unmanaged VPS hosting leaves on your desk

You get root and nothing else above the hypervisor. hosting.com publishes the clearest version of this split: on an unmanaged VPS, full root access and free choice of Linux are yours, and so are OS and control panel updates, monitoring for CPU/disk/uptime, security patching, and backups (optional rather than included). The provider keeps the datacenter, power, network uplinks, RAID storage and a 99.9% hardware/network SLA. Their managed tier is the mirror image, with proactive SRE support and 99.95%+ SLA, and no root access at all.

Root is the part people miss when they compare prices. If your stack needs kernel modules, a custom init, or a package version the host doesn't support, unmanaged is the only tier that will let you do it. If it doesn't, you are paying for a permission you won't use.

Support has boundaries even where it exists. Contabo states plainly that it doesn't manage the server for you, that support runs 8:00–23:00 German time, 365 days a year, and that project-specific configuration problems are a case for hiring a system administrator. Liquid Web defines unmanaged support as hardware, network and virtualization platform only, with OS errors, software conflicts and most configuration issues left to the customer. Vultr's support scope is worth reading on its own site before you commit, because "unmanaged" is a spectrum and the cheap end of it is very cheap indeed. 👉 [See what Vultr's plans include before you commit](https://bit.ly/VuLtr)

## The number on the pricing page is not your monthly cost

Liquid Web's comparison makes the point better than any calculator: compare total operating cost, not the monthly server price. The $24 plan costs $24 only if your time is free. Add the hours you spend on patching, monitoring, backup scripts and the 2 a.m. page when a container eats the disk, and the gap between unmanaged and managed narrows fast for anyone billing hourly.

Watch the term structure too. Contabo advertises its CLOUD VPS 8 at €11.20/mo, but that price is explicitly "for the first 24 months" against a €14.00 standard rate, so the discount is a contract length, not a permanent price. Vultr's listed rates are month-to-month prices with no separate promotional term attached, which makes the arithmetic easier. Confirm the billing term and renewal rate on the order page regardless of which host you pick.

Then there's the credit itself. Vultr's coupon page lists four offers that cannot be combined: `VULTRMATCH` (deposit matched dollar for dollar up to $100), `FLYTWOHUNDRED` ($200), `250VULTRFLY` ($250) and `FLY300VULTR` ($300). All four carry the same footnote about new customers and select products. A $300 credit is not a $300 discount on a year of hosting, and you should size your plan as if you're paying for it, because eventually you are.

## "Unlimited" is a footnote, and Vultr doesn't pretend otherwise

OVHcloud's unmanaged VPS page promises "zero restrictions on traffic volumes" and then, in the footnote, imposes monthly quotas in Asia-Pacific: 500 GB on VPS-1, 1 TB on VPS-2 and VPS-3, 3 TB on VPS-4, with speeds throttled to 10 Mbps past the limit. Contabo marks its own "Unlimited Traffic" with an asterisk. The pattern is consistent enough that you should treat every "unmetered" claim as a prompt to go find the asterisk.

Vultr meters transfer per plan instead of advertising it as unlimited: the entry-level plan carries a 2 TB monthly allowance. That's more honest and less forgiving. A 1 GB box serving images or video will burn through it, and overage gets billed. Pull the per-plan bandwidth figure before you deploy anything media-heavy, and remember that bandwidth you don't use isn't refundable.

## Where Vultr's 32 locations matter, and where they cost more

Vultr lists 32 datacenter locations across North America, South America, Europe, Asia, Africa and Australia, including Atlanta, Chicago, Dallas, Honolulu, Los Angeles, Miami, New Jersey, Seattle, Silicon Valley, Toronto, Mexico City, São Paulo, Santiago, Amsterdam, Frankfurt, London, Manchester, Madrid, Paris, Stockholm, Warsaw, Johannesburg, Tel Aviv, Bangalore, Delhi NCR, Mumbai, Osaka, Tokyo, Seoul, Singapore, Melbourne and Sydney.

Latency to your users is the reason to care, and most of those locations are priced the same. São Paulo is the exception at roughly 1.5x, which matters if you're serving Brazilian users and can live with a Miami box instead. Compare that reach with Contabo's 9 regions and 11 locations or hosting.com's 10 before deciding the location list is a tiebreaker.

## Picking a plan by workload

The list of "choose unmanaged" conditions from Liquid Web reads like a checklist for this decision: you can administer Linux, you need an experimental stack, you want direct control over packages, you already have monitoring and backup processes, you can respond when something breaks, it's a lab environment, or the lowest base price is the priority. Their table also shows where unmanaged is the wrong answer: business websites, ecommerce, agency hosting and SaaS production all start at managed.

Applied to Vultr's plans:

- **Learning, CI runners, a VPN endpoint, a personal lab.** HP 1 GB at $6. You will hit the RAM ceiling running a database alongside an app server, so keep it single-purpose.
- **One low-traffic site with caching in front.** HP 2 GB at $12. The extra gigabyte is what lets MySQL and PHP-FPM coexist without swapping.
- **Staging plus production on one box, or Docker with a handful of containers.** HP 4 GB at $24. Two cores matter more than the RAM here, because a single core will queue during deploys.
- **A small SaaS with Postgres, Redis and an app server.** HP 8 GB at $48. It's the first tier where 4 vCPUs let you isolate the database from the app.
- **16 GB at $96.** Buy it if the alternative is two smaller boxes you'd have to network together, or if you're running JVM workloads and heavy build jobs. For a websites-only workload it's overkill.

Agencies are where the industry disagrees with itself. HostPapa markets unmanaged VPS specifically at agencies running multiple client sites on one server, while Liquid Web and hosting.com both route agency hosting toward managed. The deciding question isn't the plan, it's whether someone is contractually on call when a client's site goes down at 2 a.m.

One thing that doesn't change with plan size: if the workload is a business-critical site or a store where downtime costs revenue, the honest recommendation is managed hosting, even for a competent sysadmin. Liquid Web says this outright and they sell both.

## How Vultr sits against the alternatives

Contabo gives you far more RAM per euro, an 8 vCPU / 24 GB box at €11.20/mo for the first 24 months, and correspondingly thinner support hours. OVHcloud covers the widest OS list of the three, including Windows Server 2016/2019/2022, and preinstalls cPanel, at the cost of those Asia-Pacific traffic quotas. hosting.com runs AMD EPYC with NVMe across 10 locations and backs hardware and network with a 99.9% SLA, with 99.95%+ if you move to managed. Vultr's position in that group is NVMe on every plan, the widest location list, and month-to-month pricing without a promo cliff.

## Before you enter a card

Three things to settle on the order page rather than in a review: the billing term and what the rate becomes after any introductory period; whether the instance type you chose is one of the products the credit applies to, since `FLY300VULTR` covers select products only and won't combine with other offers; and whether backups are included or a paid add-on, because snapshots are the first thing people forget to budget for and the first thing they need.

If your answer to "who fixes this at 2 a.m.?" is you, pick a plan from the table by workload and keep the box small until something actually runs out. 👉 [Start with Vultr's current plans and pricing](https://bit.ly/VuLtr)
