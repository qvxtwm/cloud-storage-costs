# cloud data storage providers: how to compare real costs beyond the sticker price, and when Sharktech's flat $4.90/TB S3 storage makes sense for backups and archives

Most people searching for cloud data storage providers are actually trying to answer one question: what will this cost me per month, really? Not the headline storage price — the full bill, including the egress fees and per-request charges that half the industry buries on a separate pricing page. This article breaks those costs down, compares the main options side by side, and explains where a lesser-known provider called Sharktech fits in: it sells S3-compatible object storage at a flat $4.90/TB/month with no request fees, which is hard to ignore if your use case is backups, archives, or DevOps artifacts. It also explains when it's the wrong choice.

## Quick picks, if you're in a hurry

> **Backing up files, databases, or VM images with an S3-compatible tool (rclone, Restic, Veeam, Duplicati)?** Sharktech's 1 TB starter plan is $4.90/month with 1 TB of bandwidth included and no request fees — the cheapest fully S3-compatible option in the comparisons we checked. 👉 [Order the 1 TB plan at $4.90/mo](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626)
>
> **Need a full backup server you control?** Sharktech's Public Cloud Small (300GB SSD, 4 vCPU, 8GB RAM, 20TB outgoing traffic) is listed at $39.00/month on third-party reviews — check the live configurator for the current figure.
>
> **Want managed backup for company devices and full systems?** The Acronis Backup Service starts at $4/month including 200 GB of cloud storage.
>
> **Just need to sync documents across devices?** Object storage is the wrong tool — a file-sync service fits better, and Sharktech doesn't sell that as a consumer product.

## "Cloud data storage" means three different products — and the pricing works differently for each

Search results for cloud data storage providers mix together offerings that only overlap in name. Knowing which one you're buying matters more than which brand you pick.

**Object storage (S3-compatible).** You get buckets and objects accessed over an API. Tools like rclone, Restic, Duplicati, Veeam, MinIO clients, and CI/CD pipelines talk to it natively. This is what you want for server backups, VM images, media libraries, log archives, and build artifacts. Pricing is usually per GB stored, plus request fees, plus egress.

**Block/cloud server storage.** Disks attached to VMs — NVMe, SSD, HDD tiers. Fast, but priced accordingly, and usually billed per GB with performance guarantees. Sharktech sells this as part of its Public Cloud, not as the storage product itself.

**Consumer sync storage.** Dropbox-style folder syncing. Fine for documents, wrong for server backups — most of these services throttle or prohibit that use.

Sharktech, a hosting company running since 2003 with data centers in Los Angeles, Las Vegas, Denver, Chicago, and Amsterdam, plays in the first two categories. Its flagship storage product is the S3 Object Storage service, and it's built on a deliberately simple commercial model — in the company's own words, storage capacity and data transfer are the only two things on the bill.

## Sharktech's full storage and backup plans

The S3 Object Storage pricing is linear: $4.90 per TB per month at every size, with bandwidth bundled alongside storage (the 1 TB tier includes 1 TB of monthly outbound transfer). The 1 TB tier is a self-serve cart configuration; larger sizes are the same flat rate, and anything above 100 TB of storage or 300 TB of monthly transfer goes through their sales team.

| Plan | What you get | Price | Billing | Order |
| --- | --- | --- | --- | --- |
| S3 Object Storage – 1 TB | 1 TB storage, 1 TB outbound transfer, S3 API, redundant HDD cluster with NVMe cache | $4.90/mo | Monthly | [Order 1 TB plan](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626) |
| S3 Object Storage – 10 TB | 10 TB storage, matching outbound transfer | $49/mo | Monthly | [Open order page](https://bit.ly/SharKtech) |
| S3 Object Storage – 100 TB | 100 TB storage, matching outbound transfer | $490/mo | Monthly | [Open order page](https://bit.ly/SharKtech) |
| S3 custom | Above 100 TB storage or 300 TB transfer | Contact sales | Custom | [Open order page](https://bit.ly/SharKtech) |
| Acronis Backup – monthly | 200 GB cloud storage, per-device backup, single-file or full-system restore | $4/mo | Monthly | [Open order page](https://bit.ly/SharKtech) |
| Acronis Backup – quarterly | Same, 3 months | $8/quarter | Quarterly | [Open order page](https://bit.ly/SharKtech) |
| Acronis Backup – semi-annual | Same, 6 months | $12/6 months | Semi-annual | [Open order page](https://bit.ly/SharKtech) |
| Acronis Backup – annual | Same, 12 months | $24/yr | Annual | [Open order page](https://bit.ly/SharKtech) |

On top of the included 200 GB, Acronis backup storage is billed per extra GB, and Sharktech also sells a Public Cloud line (OpenStack-based VMs) that some people use to run their own backup servers. The figures below come from third-party reviews rather than Sharktech's own price list, so treat them as indicative and confirm on the order page:

| Public Cloud plan | Storage | Resources | Outgoing traffic | Listed price |
| --- | --- | --- | --- | --- |
| Tiny | Configurable (NVMe/SSD/HDD) | Small resource pool | 5 TB | $7.95/mo (~$3.98/mo billed annually, per third-party reviews) |
| Small | 300 GB SSD | 4 vCPU, 8 GB RAM, 1 IPv4 | 20 TB | $39.00/mo — [order Small here](https://portal.sharktech.net/cart.php?a=add&pid=771&carttpl=proxmox_cart&configoption%5B2350%5D=17766&billingcycle=monthly&aff=1626) |
| Medium | 800 GB SSD | 8 vCPU, 16 GB RAM, 1 IPv4 | 20 TB | $79.00/mo |
| Fixed-Price XS | 500 GB SSD | 8 vCPU, 16 GB RAM, 1 IPv4 | 20 TB | $86.23/mo |
| Fixed-Price S | 500 GB SSD | 16 vCPU, 32 GB RAM, 1 IPv4 | 20 TB | $140.95/mo |

Two honesty notes on those tables. The 1 TB S3 and Public Cloud Small configurations come straight from live order pages; the intermediate S3 sizes are simple multiplications of the flat rate, which the linear pricing model makes safe to assume — but the checkout page is the final word, and Sharktech states that final pricing is confirmed at checkout. Bandwidth beyond the included 1 TB on the starter tier is listed at $0.90/TB on the official product page, and the exact bundled allocation for each size is shown in the configurator before you pay.

On discounts: Sharktech runs periodic promotions — coupon aggregators currently list up to 20% off public cloud for new customers, 15% off bare metal monthly plans, and 25% off annual bare-metal prepay — but none of the currently tracked offers apply to S3 storage specifically. The company doesn't publish a standing storage discount code, so be skeptical of any code you find on review sites and simply check the cart page for current pricing. 👉 [Check current storage pricing at checkout](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626)

## The real cost: where other providers get you is egress and request fees

Sticker prices for cloud storage look similar until you read the fine print. Four variables decide your actual bill: storage per GB, request charges, ingress, and egress. Most comparison articles list the first one and skip the rest — which is exactly backwards, because for backup workloads the egress bill is frequently larger than the storage bill.

Here's how the established options compare, based on their published rate cards (figures rounded, and worth re-checking since these change periodically):

| Provider | Storage price | Egress | Request fees |
| --- | --- | --- | --- |
| AWS S3 (Standard) | ~$0.023/GB (~$23/TB) | $0.09/GB, first 100 GB/mo free | $0.005 per 1,000 requests |
| Google Cloud Storage | ~$0.02/GB (~$20/TB) | ~$0.12/GB | ~$0.005 per 1,000 |
| Cloudflare R2 | ~$0.015/GB (~$15/TB) | Free | Small Class A/B fees |
| Wasabi | $7.99/TB (pay-as-you-go) | Free (fair use) | None, but 90-day minimum storage duration |
| Backblaze B2 | ~$0.006/GB | Free up to 3x stored data, then $0.01/GB | First 2,500/day free per class |
| DigitalOcean Spaces | $5/mo for 250 GB, ~$0.02/GB beyond | 1 TB included, then $0.01/GB | None |
| **Sharktech** | **$4.90/TB flat** | 1 TB included on starter tier, then $0.90/TB | None |

Do the math on a 10 TB backup archive. On Sharktech: $49/month, with a matching download allowance. On AWS S3 Standard: roughly $230/month for the storage alone, before a single restore. Pull that whole archive down once from AWS and you're adding around $900 in egress — which is why switching providers can feel like a hostage negotiation. Sharktech's overage rate of $0.90/TB applies only to what you download beyond your bundled allowance, and inbound traffic is free across this comparison.

The request-fee line matters more than people expect, too. Nightly backup jobs, Restic chunking, and CI/CD pipelines generate thousands of API calls per run. AWS and Google meter those; Sharktech and Wasabi don't. For a chatty backup schedule, request fees alone can add several dollars a month on the hyperscalers.

Where Sharktech's rate sits in context: at $4.90/TB it undercuts Wasabi's $7.99 pay-as-you-go rate by about 40%, comes in at roughly a third of Cloudflare R2's, and around a fifth of the big three's. Third-party analyses estimate the savings on a 10 TB archive versus the hyperscalers at $200–450 per month, storage only.

## What Sharktech's object storage doesn't do — read this before ordering

Sharktech's product page is unusually blunt about this, and it's the part most roundups skip: the service is described as "a capacity-first object storage service, not an all-flash block-storage replacement." Technically it's high-capacity HDD storage with an NVMe cache layer, exposed through the S3 API. That design is why the price is low, and it shapes what the service is for.

It's the wrong tool if your application needs any of the following:

- A **boot disk** or filesystem semantics — you need block storage or a file server, not object storage
- Consistently **low-latency block storage** for a live database — same answer
- **Storage classes and cross-region replication** out of the box — both exist, but only via their sales team, not the self-serve panel
- Extreme request throughput (millions of PUT/GETs per second) or a bundled CDN — you'd pair it with a CDN yourself

Also note the >100 TB ceiling on self-serve: beyond that, or if you want quarterly/annual billing on big volumes, it's a sales conversation.

None of these are dealbreakers for the core audience — offsite backup, archive, and artifact storage — but if you came here looking for hot application storage, you now know to stop reading and look elsewhere. Meanwhile, on the features that backup tools actually exercise, the checklist is solid: bucket policies and ACLs, versioning, object locking for retention, lifecycle rules for auto-expiry, presigned URLs for time-limited sharing, multipart uploads with integrity checks, plus CORS, event notifications, object tagging, and access logging.

If that matches what you need, the setup is deliberately boring: the service speaks standard S3, so any tool you already use keeps working. 👉 [Open the S3 Object Storage order page](https://bit.ly/SharKtech)

## Acronis Backup: the managed option, with one pricing quirk

Object storage assumes you can wire up a backup tool. If you'd rather have the whole stack managed — agents for laptops, servers, even phones, with a web console and mobile app, encryption and compression built in, and the ability to restore a single file or an entire machine — Sharktech resells Acronis-based backup hosting starting at $4/month including 200 GB of cloud storage.

The billing table is where it gets interesting. Annual prepay costs $24 — that's $2/month, half of what monthly billing ($4/month, or $48/year) adds up to. No complaints there. But the per-GB overage rate moves in the opposite direction from what you'd expect: $0.02/GB on monthly billing versus $0.12/GB on annual, according to the numbers on Sharktech's announcement page. That pattern is odd enough that we'd treat the overage figures as listed-but-verify — if you expect to exceed the included 200 GB by a lot, confirm the overage rate for your chosen term before committing. At current prices, monthly billing with the cheap overage may actually beat annual if your dataset is several times the included allowance.

For context on the "half the cost" claim Sharktech makes about this service: Acronis backup through mainstream MSPs typically runs well above $4/month per workload, so the claim is plausible, but we didn't find independent verification of a like-for-like comparison.

## Getting started takes one cart page and an access key

There's no onboarding ceremony. The practical sequence:

1. Pick your size on the S3 Object Storage order page (the 1 TB tier is the self-serve default; the configurator handles other sizes).
2. After provisioning, generate S3 credentials from your Sharktech portal.
3. Point your tool at the endpoint — rclone, Cyberduck, Nextcloud, S3 Browser are officially listed, and Restic, Duplicati, Veeam, MinIO clients, Terraform, and Jenkins/GitLab pipelines all work through the standard S3 API. Each location has 40G inbound/outbound connectivity per the published specs.
4. Set a lifecycle rule on day one. Backup repos grow forever; auto-expiring old objects is the difference between a $4.90 bill and a surprise.

Two practical expectations worth setting. First, provisioning: user feedback collected on coupon and review aggregators averages 4.1 out of 5 across a small number of reviews, and the recurring compliment is that the DDoS protection genuinely works under attack — the recurring complaint is provisioning time, with some users reporting VPS activation taking several hours to nearly a day rather than minutes. Plan your setup window accordingly. Second, billing is month-to-month by default with no long-term contract on the self-serve tiers; quarterly or annual terms for larger volumes go through the sales team.

## FAQ

**Is $4.90/TB with no request fees actually sustainable, or is there a catch?**
The catch is the hardware trade-off described above: HDD capacity with NVMe caching instead of all-flash arrays, which is exactly the right trade for backup and archive workloads and the wrong one for hot databases. The pricing itself has no minimum storage duration and no contract lock-in on the self-serve plans.

**Can I get my data out if I leave?**
Yes, and this matters. Standard S3 API access, object locking for retention control, and the bundled bandwidth mean a full restore of 1 TB of data costs you nothing beyond your monthly plan. There's no proprietary format to escape from.

**What about the Public Cloud plans for running my own backup stack?**
Third-party reviews put the Tiny plan at $7.95/month (about half that on annual billing) for a lightweight self-hosted backup server, with Small at $39/month suited to a small-business restore environment. VM disk images can be downloaded in full, so migration out is straightforward. Confirm both figures on the live configurator. 👉 [See the Public Cloud Small configuration](https://portal.sharktech.net/cart.php?a=add&pid=771&carttpl=proxmox_cart&configoption%5B2350%5D=17766&billingcycle=monthly&aff=1626)

**How does Sharktech compare to Wasabi, since both advertise flat pricing?**
Wasabi's current pay-as-you-go rate is $7.99/TB/month with no egress or API request fees, a 90-day minimum storage duration per object, and a monthly minimum tied to 1 TB of active storage; it also sells reserved capacity blocks on 1-, 3-, or 5-year contracts starting at 25 TB. Sharktech is $4.90/TB with 1 TB of bundled egress on the starter tier, no minimum storage duration, and no contract. If you retrieve far more data than you store every month, Wasabi's free egress can win; for typical backup patterns — write a lot, restore rarely, delete old snapshots when you like — Sharktech is cheaper and less restrictive.

## Which provider to pick, based on your situation

- **Backing up servers, databases, or VM images, and you want the lowest storage cost with predictable billing:** Sharktech's S3 Object Storage at $4.90/TB is the cheapest fully S3-compatible rate in every comparison we checked, and the 1 TB tier is self-serve. 👉 [Order the 1 TB S3 plan for $4.90/mo](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626)
- **Restoring large amounts of data frequently:** the free-egress options — Wasabi (fair use, but 90-day minimum storage) or Backblaze B2 (up to 3x stored data) — may edge out Sharktech once your monthly downloads exceed the bundled allowance, though check their request fees and minimum-storage terms first.
- **Running a live database or latency-sensitive app on the storage:** none of the budget options fit; you want block storage from a cloud platform, and Sharktech says as much on its own product page.
- **Managed backup for a small team's devices with no DevOps time:** Sharktech's Acronis Backup at $4/month including 200 GB, with an unusually cheap annual rate of $24, is worth a look — just confirm the overage pricing for your term first.

Before you click order, verify two things on the checkout page: the final price (Sharktech confirms it at checkout) and the exact bandwidth allocation for your chosen size. Both take thirty seconds and remove the only two surprises left in this purchase.
