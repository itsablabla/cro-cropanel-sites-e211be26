# Missing Review Count — dev spec
Site: allbirds.com · Priority 9 · High · Effort: Medium (2-5 days)

## Problem
The product page shows a reviews section but no visible review count or rating summary, leaving buyers without social proof at the decision point.

## Evidence (from the live site)
> H2s include 'Reviews for Anytime Ankle Sock' but no review count or star rating appears in the body sample or CTAs.

## Current state
h1: Anytime Ankle Sock; cta: Get Notified; notes: Reviews section exists but lacks visible aggregate rating or count.

## Required change
h1: Anytime Ankle Sock; cta: Add to Cart; notes: Add a review summary near the price or CTA, e.g., '4.8/5 from 2,300+ reviews' to provide immediate social proof.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Add a review summary near the price or CTA, e.g., '4.8/5 from 2,300+ reviews' to provide immediate social proof.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_missing_review_count` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 299,882 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; not testable at current traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
