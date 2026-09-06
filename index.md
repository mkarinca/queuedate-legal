# Privacy Policy

**App:** QueueDate (the "App")
**Last updated:** 2026-09-06

This policy explains exactly what data the App collects, why, how long it is
kept, and who it is shared with. It covers only the App itself — not the
Shopify platform or your store's own privacy practices.

## Who this applies to

The App is installed by Shopify merchants. It does not have its own user
accounts or logins. "You" below means the merchant who installs the App.

## What we collect and store

When you install the App and configure it, we store the following in our
database:

| Data | Purpose |
| --- | --- |
| Your shop domain (e.g. `your-store.myshopify.com`) | Identifies which store a set of settings and API credentials belongs to. |
| Shopify access token and session record | Lets the App call the Shopify Admin API on your store's behalf. The session record may also include the name and email of the staff user who authenticated, as supplied by Shopify during login. |
| Daily production capacity | Input to the delivery-estimate calculation. |
| Transit days | Input to the delivery-estimate calculation. |
| Working days | Input to the delivery-estimate calculation. |
| Carrier delivery days | Input to the delivery-estimate calculation. |
| Cutoff time (hour and minute) | Input to the delivery-estimate calculation. |
| Shop timezone | Input to the delivery-estimate calculation. |
| Closure dates (start date, end date, optional label) | Workshop closures (holidays, annual leave) that the delivery-estimate calculation skips over. |

Every one of these values is entered by you, or issued to the App by Shopify
during installation. All of it is scoped to your shop.

## What we read but do not store

To show a delivery estimate, the App reads the **count of unfulfilled orders**
on your store from the Shopify Admin API, in real time, each time an estimate
is calculated. This count is used immediately and is not written to our
database.

The App does **not** collect, receive, or store:

- Order contents, line items, or order details
- Customer names, addresses, emails, phone numbers, or any other customer
  personal information
- Payment or billing details (subscription billing is handled entirely by
  Shopify; the App only reads whether an active subscription exists)

## Why we need Shopify permissions

The App requests the `read_orders` scope solely to read the unfulfilled order
count described above. Other scopes it requests are used for the App's
storefront block and configuration, not for collecting personal data.

## How long we keep it

We keep your shop domain, credentials, settings, and closure dates for as long
as the App is installed. We do not run separate backups of this database beyond
what our hosting provider performs for infrastructure resilience.

## Deletion when you uninstall

When you uninstall the App, Shopify sends an `app/uninstalled` webhook. On
receiving it, the App immediately deletes:

- Your session records and access token
- Your settings
- Your closure dates

As a backstop, Shopify also sends a `shop/redact` webhook approximately 48
hours after uninstall. On receiving it, the App again deletes all settings,
closure dates, and session records for your shop. After that, we retain
nothing about your store.

## GDPR / CPRA compliance webhooks

Shopify requires apps to handle three mandatory compliance webhooks. The App
implements all three:

- **`customers/data_request`** — A request for a customer's stored data. The
  App stores no customer personal data, so it has nothing to return and
  acknowledges the request.
- **`customers/redact`** — A request to delete a customer's data. The App
  stores no customer personal data, so there is nothing to delete and it
  acknowledges the request.
- **`shop/redact`** — A request to delete a shop's data after uninstall. The
  App deletes all settings, closure dates, and session records for the shop,
  as described above.

All webhook requests are verified with Shopify's HMAC signature before any
action is taken; unsigned requests are rejected.

## Third parties

Your data is shared with only two categories of third party:

- **Shopify** — The App runs as a Shopify app and communicates with the
  Shopify Admin API. Shopify's handling of your and your customers' data is
  governed by Shopify's own privacy policy.
- **Our hosting provider** — The App and its database run on infrastructure
  operated by Railway (railway.app), who processes the stored data on our
  behalf solely to host the service.

We do not sell your data, share it for advertising, or send it to analytics,
tracking, or marketing services.

## Security

Access tokens and settings are stored in our application database on our
hosting provider's infrastructure. Access to that infrastructure is limited to
the people who operate the App. Communication with Shopify uses HTTPS.

## Changes to this policy

If we change what the App collects or how it is used, we will update this page
and change the "Last updated" date above.

## Contact

Questions about this policy or your data:

**queuedate.support@gmail.com**
