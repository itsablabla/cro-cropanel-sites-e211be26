# Out-of-Stock Form Missing Size — dev spec
Site: allbirds.com · Priority 8 · High · Effort: Medium (2-5 days)

## Problem
The product page for the Anytime Ankle Sock shows a 'Get Notified' CTA, indicating the item is out of stock, but the form likely only captures an email, missing the opportunity to capture size preference and reduce future friction.

## Evidence (from the live site)
> The product page CTAs include 'Get Notified' and the h1 is 'Anytime Ankle Sock'. The form inventory for this page was not fully captured, but the presence of 'Get Notified' suggests a back-in-stock alert form.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Out-of-stock alert form likely captures only email, missing size preference.

## Required change
h1: Anytime Ankle Sock; cta: Get Notified When Back in Stock; notes: Include a size selector in the notification form to capture size preference, enabling more targeted restock alerts and reducing friction when the item returns.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Include a size selector in the notification form to capture size preference, enabling more targeted restock alerts and reducing friction when the item returns.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_out_of_stock_form_missing_size` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
