# Google Business Profile categories and services, by country

The complete list of Google Business Profile (GBP) categories, with the services Google predefines for each one, for every country Google supports. Free to use as CSV and JSON.

- **4,375 categories** and **6,410 predefined service types** across **242 countries and regions**
- Refreshed from Google's API on 31 October 2026
- A [changelog](CHANGELOG.md) of the categories Google has added, removed and renamed

Maintained by [Jepto](https://www.jepto.com).

## Quick answers

**How many Google Business Profile categories are there?**
4,375 across all countries. Any one country has about 4,040 to 4,180 of them, for example 4,051 in the US, 4,050 in Australia and 4,066 in the UK.

**How many categories can a business profile have?**
One primary category and up to nine additional categories.

**Are the categories the same in every country?**
Mostly, but not exactly. About 4,040 categories are available in almost every country, and the rest are limited to some. Display names can differ by language and locale. The `regions` column in `data/categories.csv` shows where each category is available. Google returned no categories for CN, CU, IR, KP, SD and SY.

**Does every category come with services?**
No. Only about 440 categories in any one country have predefined services (533 across all countries), such as "Faucet installation" under Plumber. Businesses can also add their own custom services, which aren't in this list.

**What does a category ID look like?**
`gcid:plumber`, `gcid:italian_restaurant`. The ID stays the same when Google renames a category, so use it as the key.

**How often does the list change?**
Google adds, renames and removes categories through the year. Every refresh adds an entry to the [changelog](CHANGELOG.md).

**Where do these categories come from?**
Google's Business Information API, which returns categories one country and language at a time. This list merges every region into one set of files.

## The data

All files are in [`data/`](data/).

| File | One row per | Columns |
|---|---|---|
| `categories.csv` | category | `gcid`, `category`, `region_count`, `service_count`, `regions` (country codes separated by `;`) |
| `category_services.csv` | category + service type | `gcid`, `category`, `service_type_id`, `service` |
| `categories.json` | category (nested) | name, regions, services |
| `attributes.csv` | attribute | `attribute_id`, `attribute`, `group`, `category_count` |
| `category_attributes.csv` | category + attribute | `gcid`, `category`, `attribute_id`, `attribute`, `group` |

`gcid` is Google's category ID, for example `gcid:restaurant`. Names are in English.

Attribute files are a US English (en-US) export from the Jepto GBP Discovery tool, covering 192 attributes across 4,099 categories. They are a separate snapshot from the category files, so the two sets do not match exactly: 115 categories appear only in the attribute files, and 391 categories in `categories.csv` have no attribute rows.

## Choosing categories

- Pick the most specific category that describes your main business as the primary. A specific category like `Italian restaurant` says more than `Restaurant`.
- Add every other category that describes something you do, up to nine. Adding a category also makes its predefined services available to add to your profile.
- Check the category exists in your country in the `regions` column of `data/categories.csv` before you plan around it.
- Review the [changelog](CHANGELOG.md) now and then. Google renames and removes categories, and a removed category can leave a profile with an outdated one.

## Skip the spreadsheet: use your data in Jepto

This list is the reference. The harder part is knowing which categories and services each of your profiles actually has, and how that relates to performance. Jepto's [data model](https://www.jepto.com/data-model) already does that.

- **All your data, one way in.** Every location's primary and additional categories, primary and additional services, reviews, posts, search keywords and performance sit in one model, next to your other marketing data.
- **Nothing to maintain.** You don't download files, run scripts or watch for Google's changes. Jepto syncs your profiles and keeps the data current for you.
- **Use it where you work.** Build reports in Jepto, or ask questions of the same data from an AI assistant through [MCP](https://www.jepto.com/integration/mcp).

Where to go next:

- [Local Listings](https://www.jepto.com/local-listings): audit categories and services across every profile and update them in bulk.
- [GBP Discovery tool](https://www.jepto.com/tools/gbp-discovery): browse categories and services and filter by attribute.
- [Google Business Profile data source](https://www.jepto.com/data-warehouse/google-business-profile): the metrics and fields available, with the [help article](https://www.jepto.com/help/data-source-google-business-profile).
- [Category and Service List](https://www.jepto.com/help/category-and-service-list): background on the Jepto list.
