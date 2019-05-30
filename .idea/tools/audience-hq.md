# Pricing ideas
Higher plans
- longer lookback window
- ad-hoc backfills
- setup calls - site tagging, audience definitions etc
- Metabase instance setup?

Stuff that could happen even without client side integration:
- Daily emails with audience volumes, changes in volumes and trends
- Send all IDs and segments into BigQuery for BigQueryML auto-generated insights and segments

Automations:
- tag setup in GTM

# Marketing
Use backfill as a feature that can be enabled for certain promo code signups

# Client side notes
- Sync and save segments, similar to how we do in `fn-fetch-user-segments`.
- Assign segments to the account via a relation
- User can only modify segments on the account if they own them, but they can see the users who own the other segments attached to the account

- A user can generate multiple tokens for **different projects** but they should not have two tokens that are different google accounts. This will mean that some syncs will use one set of segments and other syncs will fetch another set of segments. If they are different projects (for API/billing etc), there is no problem.
- When a user wants to use a seperate account, they'll need to sign in with that account and associate the Google ID
- i.e. there is a *1-to-1 mapping between our user accounts and google accounts*.