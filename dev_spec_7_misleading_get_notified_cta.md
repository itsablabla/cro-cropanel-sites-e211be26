# Misleading Get Notified CTA — dev spec
Site: allbirds.com · Priority 7 · Urgent · Effort: Medium (2-5 days)

## Problem
The 'Get Notified' CTA on a product page for an in-stock item creates a bypass that may lead to lost sales if the item is actually available.

## Evidence (from the live site)
> The product page for Anytime Ankle Sock includes a 'Get Notified' CTA, which is typically for out-of-stock items; the inventory shows prices and size selectors exist, implying the item is purchasable.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: If the item is in stock, 'Get Notified' is a misleading CTA that sends users to a notification signup instead of adding to cart.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Replace 'Get Notified' with 'Add to Cart' if the item is available; only show 'Get Notified' when truly out of stock.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Replace 'Get Notified' with 'Add to Cart' if the item is available; only show 'Get Notified' when truly out of stock.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_misleading_get_notified_cta` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
