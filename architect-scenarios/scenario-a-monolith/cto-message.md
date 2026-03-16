# Message from the CTO

*Sent to the architecture team, February 2026. Lightly edited for clarity.*

---

Hi all,

I've been putting off writing this for a while, but after last Wednesday's deployment incident I think we need to have an honest conversation about where ShopCore is going.

We're not in a crisis. The system works, customers are happy (mostly), and we're shipping features. But we're also getting slower. Deployments that used to take 40 minutes now take nearly two hours. We had three merge conflicts last sprint that required half a day to untangle. Two of our best engineers have told me in 1-on-1s that they find the codebase frustrating to work in. That's a warning sign I take seriously.

I don't want to do a big rewrite. We've all seen how those end. But I also don't think we can keep patching this indefinitely.

What I want from the architecture team is a clear picture of where we should be heading. Not a detailed migration plan — I know that'll take longer to work out. But a direction. Something I can put in front of the board and say "this is where ShopCore is going over the next two to three years, and here's why."

A few things I care about:

**Teams should be able to work independently.** Right now, every sprint has at least one situation where Team Catalog is waiting on something Team Orders needs to change first. That has to stop. I want teams to be able to deploy their own piece without coordinating a release window.

**The payment module needs to stop being a black box.** I understand why nobody wants to touch it, but we can't have a core part of the system that's effectively frozen because it's too scary. Whatever direction we go, we need a plan for payment.

**We need to be able to hire.** When I talk to candidates about our stack, "PHP monolith with jQuery" is not a selling point. I'm not saying we rewrite everything in TypeScript tomorrow, but our technology choices need to be defensible.

**I don't want to break what works.** We do 40,000 orders a day. Any changes have to be done in a way that doesn't put that at risk. We cannot take the system down.

What I'm not prescribing is how we get there. Microservices, modular monolith, event-driven, strangler fig — I've heard arguments for all of them and I genuinely don't know which is right for us. That's what I'm asking you to figure out.

I'd like to see a draft direction document before the end of Q1. Not a 50-page architecture spec — a clear statement of where we're going and why, with the key decisions we need to make identified.

Thanks,
Henrik
