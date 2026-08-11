# Missing H1 on Collection — dev spec
Site: allbirds.com · Priority 4 · High · Effort: Low (0.5-2 days)

## Problem
The 'Shop All' collection page lacks an H1 heading, leaving the page without a clear semantic anchor for both users and search engines, and the title 'SHOP ALL '26' is generic and doesn't communicate the value or purpose of the collection.

## Evidence (from the live site)
> h1s: [] (empty array) on /collections/shop-all-26; title: 'SHOP ALL '26'

## Current state
h1: None; cta: Apply filters; notes: The page has no H1, which is a missed opportunity for SEO and user clarity. The title 'SHOP ALL '26' is generic and doesn't convey the range or benefits of the products.

## Required change
h1: Shop All Shoes & Apparel; cta: Filter by Category; notes: Add a clear H1 that describes the page content and includes relevant keywords. The CTA should be more descriptive, guiding users to filter or explore categories.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a clear H1 that describes the page content and includes relevant keywords. The CTA should be more descriptive, guiding users to filter or explore categories.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_h1_collection` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
