# Elastic Web Agentic Analytics: Manager Guide

## Executive overview

This dashboard explores how to measure an AI agent's work from the moment it receives a request through execution and outcome review. It also demonstrates how a metric can show its source, calculation, evidence, and verification status.

The current dashboard is a static prototype with illustrative sample values. It is not connected to live Elastic Web agent events.

## 1. Starting point: Verify before publishing

The Instinct proposal starts with a trust question: how do we know that a dashboard claim is supported by evidence?

It proposes a reusable review process for every claim or metric. The record should show:

- The claim or metric and its source.
- Who reported it, where it appeared, when it was collected, and how it was gathered.
- The evidence and calculation checks used for that kind of claim.
- The result, including its limits and any missing evidence.
- What could not be checked, what was omitted, and why.
- A traceable record of how the review was performed.

The proposal also requires a separate safety check for incoming pages, files, and prompts. Passing that check does not prove a claim is true. Verifying a claim does not make instructions inside its source safe.

## 2. Why Agentic AI needs this view

Conventional analytics helps teams understand search visibility, website visits, engagement, leads, and revenue. Agentic analytics adds a view of what an AI agent does while trying to complete a task.

The journey represented here is:

**Request received → capability selected → tool executed → outcome checked → evidence recorded**

This can help teams understand whether agents find a relevant capability, where tasks fail, how long execution takes, and whether reported outcomes have supporting evidence. Agentic analytics can complement existing web and business analytics.

## 3. Dashboard sections

1. **Overview:** Headline activity, completion, timing, and evidence indicators.
2. **Executions:** Sample execution and completion trends over time.
3. **Discovery tests:** A synthetic example of capability selection.
4. **Capabilities:** A sample breakdown by execution path.
5. **Recipes:** The request-to-outcome funnel.
6. **Evidence & hashes:** Example fingerprints and provenance information.
7. **Integrations:** Example execution records and their reported outcomes.

## 4. Headline metrics

Every value below is illustrative prototype data, not a measurement from live agent activity.

1. **Agent executions: 1,284**  
   Intended to count distinct task or execution IDs in the displayed period, with retries deduplicated. Raw events are not attached, so the count cannot be reproduced from a source feed.

2. **Task completion: 84.6%**  
   The dashboard describes this as outcome-evaluated runs divided by started runs. The funnel shows 1,087 outcomes verified from 1,284 starts, which rounds to 84.7%. The review panel flags the discrepancy for reconciliation.

3. **Median completion: 2.4 seconds**  
   Intended to measure elapsed time from intent received to task completed. A 0.3-second improvement is also shown. Live timestamps are required to verify these values.

4. **Evidence captured: 96.1%**  
   Intended to describe completed runs with a provenance record. The precise denominator needs to be agreed and verified against real event data.

## 5. Funnel and supporting charts

The sample intent-to-outcome funnel shows:

- 1,284 intents received.
- 1,194 capabilities selected.
- 1,130 tools completed.
- 1,087 outcomes verified.

These counts illustrate where tasks may drop out. For example, 90 requests fall between intent received and capability selected.

The execution trend uses fixed sample dates from September 24–30, 2026. The execution path chart shows sample shares of 68% remote, 17% local device, and 15% needing review. The discovery benchmark shows 62% capability selection and 38% other or none. It is labeled synthetic and describes a controlled suite of 120 prompts across three model configurations, not live traffic.

## 6. Evidence and example records

The Integrations section contains example rows. The Crossref row is labeled **Brief-reported** because the engineering brief reports a successful trace, but its raw event record is not attached. The other rows are also examples and should not be treated as verified live activity.

The dashboard calculates SHA-256 fingerprints for sample event and payload records. A hash can help reveal a change when compared with a separately trusted copy. A browser-calculated hash does not prove that the underlying data is true, identify which agent created it, or provide a trusted timestamp.

## 7. What the verification panel currently checks

The panel applies the proposal to one sample metric, **Agent executions**. It shows the stated source, collection method, time window, calculation, evidence reference, review status, checks, limitations, and a traceable review record.

The sample count matches the funnel start count. Raw source evidence is missing, and the completion-rate calculation is flagged. The metric is therefore labeled **Unverified**. The source-instruction safety check is **Not run** because the prototype does not ingest external pages, files, or prompts.

The panel is informational. It does not block publication and does not create a durable server-side audit record.

## 8. Current status and next steps

The dashboard is a static prototype. The next phase should:

1. Connect a real event source and capture the task journey from request through outcome.
2. Define metric formulas, time windows, retry handling, and denominators.
3. Reconcile the completion-rate discrepancy using source records.
4. Apply consistent evidence fields and status rules to all dashboard metrics.
5. Add a publishing gate so unsupported claims cannot be presented as verified.
6. Add separate prompt-injection screening if external content is ingested.
7. Use server-side hashes and a durable audit record for production evidence.

## Manager takeaway

This is a live prototype of how Agentic AI analytics could report an agent's journey and show the evidence behind its metrics. The Instinct proposal adds a verification process so a metric's source, calculation, evidence, and limitations are visible. The figures are illustrative; connecting live events and making verification enforceable are future work.

## Links

- [Live dashboard](https://elastic-agentic-analytics-verificat.vercel.app/)
- [GitHub repository](https://github.com/rajvictor1/elastic-agentic-analytics-verification)
- [Instinct proposal: Verify before publishing](https://files.instinct.com/u7hvsg8zew60-verify-before-publishing?via=wa)
