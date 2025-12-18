---
date: '2025-07-03T10:46:54-05:00'
draft: true
title: 'The Joy and Angst of Building Multi-Tenant Applications'
---

There is a conversation that I have been a part of many times. "Hey, we landed this great contract with a client! They want to use our product, and they want it to behave in drastically different ways than our existing clients. We can make that happen, right?" To which I hesitantly say, "Sure, but that'll take about six sprints of work for us to complete."

{{< callout type="tip" text="This is a tip callout." >}}

Almost always, the response to that is, "Great! What about three instead?" And thus, our fate is sealed.

This was infuriating at first - why are we supporting all these bespoke features for our different clients? Don't they know that these features take time?

And that's when it clicked. If I had taken a step back, and looked at the _nature_ of these requests, it was clear that what we were only going down **one** potential path and use case for our product. It had never occurred to me that we **could**, or even **should**, anticipate what a client may want out of our platform.

```rust
pub struct User {
    id: u32,
    name: String,
    email: String,
}

impl User {
    pub fn new(id: u32, name: String, email: String) -> Self {
        User { id, name, email }
    }
}

```

## The Original Approach

Our product was designed with a single use case in mind: we have a large database of discounts for retailers across the country, and our clients can grant access to these discounts to their customers for any arbitrary reason. Simple, right?

Where the wheels started to fall off was when clients approached us with

## Configuration vs. Constraints

Dev, Design, and Customer Success to align on what we _think_ will work for all tenants, and what they _think_ will need to be configured per-tenant.

## Designing for Multi-Tenancy

Inevitably, "the customer is always right" and dev needs to build the application in a way that allows _anything_ to change.

## Planning for Change

Who knows what a client may want?

## Final Thoughts

That's showbiz, baby.
