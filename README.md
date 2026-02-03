# GA4 Funnel & Channel Performance (BigQuery + SQL)

## Business Question
Which acquisition channels drive the highest conversion to purchase, and where are the biggest funnel drop-offs?

## Data
BigQuery public dataset (GA4 obfuscated ecommerce):
`bigquery-public-data.ga4_obfuscated_sample_ecommerce.events_*`

## What I Built
- Daily user-level funnel (session_start → view_item → add_to_cart → begin_checkout → purchase)
- Channel conversion rate (purchase users / session_start users) by source/medium
- Session-level funnel by channel using GA4 `ga_session_id`

## Key Metrics
- user_purchase_rate (user-level)
- session_purchase_rate (session-level)
- drop-off rates between funnel stages

## Files
- `sql/01_sanity_check.sql`
- `sql/02_daily_user_funnel.sql`
- `sql/03_user_purchase_rate_by_channel.sql`
- `sql/04_session_funnel_by_channel.sql`

## Recommendation (example)
Prioritize channels with higher purchase rates and investigate friction points between add_to_cart → begin_checkout for low-converting channels.
