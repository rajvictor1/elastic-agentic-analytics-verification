# Elastic Web Agentic Analytics V1

A small, static dashboard prototype for exploring how to measure an AI agent's work from request to outcome. It includes an informational review panel based on the **Verify before publishing** proposal.

## Open the dashboard

Open `index.html` in a browser. No install, account, or build step is required.

## What the review panel demonstrates

- Record a metric's source, collection method, time window, calculation, and evidence references.
- Show checks performed and identify missing evidence.
- Keep factual verification separate from prompt-injection safety review.
- Calculate a SHA-256 fingerprint for the displayed review object.

## Prototype limits

The dashboard uses fixed sample values in the HTML. It is not connected to an event feed, and it does not verify live performance. The current review panel checks one sample metric, shows no durable server-side audit record, and does not block publication. The displayed hash is an integrity fingerprint for the review object only; it is not a signature or trusted timestamp.

The sample completion figures also illustrate a calculation mismatch: 1,087 completed outcomes divided by 1,284 started executions rounds to 84.7%, while the dashboard displays 84.6%. The review panel flags this discrepancy.

## Scope

This repository contains the V1 static dashboard only. It does not include V2 or Vercel deployment settings.
