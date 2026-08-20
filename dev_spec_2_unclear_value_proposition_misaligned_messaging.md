# Unclear Value Proposition — dev spec
Site: example.com · Priority 2 · High · Effort: Low (0.5-2 days)

## Problem
The homepage copy focuses on the domain's technical purpose rather than clearly articulating the product/service's value proposition and benefits to the visitor, failing to engage potential customers.

## Evidence (from the live site)
> This domain is for use in documentation examples without needing permission.
> Avoid use in operations.

## Current state
h1: This domain is for use in documentation examples without needing permission.; notes: Page copy describes domain's technical purpose, not visitor benefits or product offering, leaving visitors without a clear offer above the fold.

## Required change
h1: Clear statement of product/service and primary benefit, visitor-centric.; notes: Rewrite copy to focus on the visitor's problem and how the offering solves it, using language that mirrors how customers describe their needs.

## Acceptance criteria
- GIVEN a first-time visitor on the affected page
- WHEN the change is live
- THEN Rewrite copy to focus on the visitor's problem and how the offering solves it, using language that mirrors how customers describe their needs.
- AND no layout regression at 375px / 768px / 1280px
- AND the changed control is keyboard-reachable with an accessible name

## Tracking
- Fire `cro_unclear_value_proposition_misaligned_messaging` on interaction with the changed element
- Verify the event fires in BOTH variants before opening traffic

## Test plan
- Two-proportion z-test, 95% significance, 80% power
- 315,206 visitors per variant to detect a 5.0% relative lift
- Run at least one full business cycle; duration depends on traffic

## Rollback
Feature-flag the change; revert if the primary metric drops for 3 consecutive days.
