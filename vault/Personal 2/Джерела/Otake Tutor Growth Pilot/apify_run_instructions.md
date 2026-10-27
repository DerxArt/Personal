# Apify Tutor Lead Scout

## What This Does

This runner searches Instagram through Apify for language tutors, fetches profile details, filters likely outreach targets, and creates:

- `apify_tutor_leads.csv` - clean list for outreach.
- `apify_tutor_leads_raw.json` - full raw data for audit.

## Default Search

The default market is `both`, so it searches:

- Ukrainian tutor queries.
- Global English tutor queries.

You can switch with:

- `APIFY_MARKET=ua`
- `APIFY_MARKET=global`
- `APIFY_MARKET=both`

## Filters

The runner keeps profiles that look like:

- Public Instagram accounts.
- 5K-500K followers.
- Recent activity if Apify returns that field.
- Tutor/teacher/language-coach related.
- Stronger priority when they use Linktree, Beacons, Calendly, bio.site, Taplink, Stan Store, Carrd, or similar.

The output also labels the outreach segment:

- Under 20K: gift/help only.
- 20K-50K: gift/help first.
- 50K+: gift/help or paid.

## Run

From the pilot folder:

```bash
export APIFY_TOKEN="your_apify_token_here"
APIFY_MARKET=both /Users/arturderda/.cache/codex-runtimes/codex-primary-runtime/dependencies/node/bin/node apify_tutor_lead_scout.mjs
```

The token is available in Apify Console under Settings - Integrations.

