# Vague Hero Copy — dev spec
Site: allbirds.com · Priority 2 · Urgent · Effort: Low (0.5-2 days)

## Problem
The hero headline 'Wildly Comfortable. Super Natural.' is abstract and feature-led, failing to directly address the visitor's intent to find comfortable, sustainable shoes, and the CTAs 'SHOP MEN' and 'SHOP WOMEN' are generic, not guiding toward a specific product or benefit.

## Evidence (from the live site)
> H1: 'Wildly Comfortable. Super Natural.' CTAs: 'SHOP MEN', 'SHOP WOMEN'

## Current state
h1: Wildly Comfortable. Super Natural.; cta: SHOP MEN / SHOP WOMEN; notes: The hero copy is abstract and feature-led, not directly addressing the visitor's intent to find comfortable, sustainable shoes. The CTAs are generic and don't guide toward a specific product or benefit.

## Required change
h1: Shoes That Feel Like Nothing Else; cta: Shop Best Sellers; notes: Use benefit-driven copy that speaks to the visitor's desire for comfort and sustainability. The CTA should be specific and action-oriented, guiding visitors to a curated collection like best sellers.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Use benefit-driven copy that speaks to the visitor's desire for comfort and sustainability. The CTA should be specific and action-oriented, guiding visitors to a curated collection like best sellers.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_vague_hero_copy` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 118,817 visitors per variant to detect a 8.0% relative lift
- Run at least one full business cycle; 40 days

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
