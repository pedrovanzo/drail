# drail

Yes, it sounds like "derail." That's the joke — comedy over accuracy. The project itself is about keeping routes on track, not going off them.

## What this is

A portfolio rebuild of a pattern I designed and ran in a private, internal setting: a lightweight, self-service app-hosting platform built around path-based reverse-proxy routing.

The core idea:

- One reverse-proxy container, one published port. Apps live behind it on an internal network.
- Each app gets routed by a URL slug (`/<slug>/`), resolved to its own container.
- Routing is **self-service**: each app's own CI pipeline publishes its own route snippet — there's no central admin hand-editing a giant config file.
- Every published snippet is validated before going live, and automatically rolled back to the last-known-good version if validation fails.
- A slug is "owned" by whichever app first claims it — another app can't silently take it over.

This repo is a from-scratch, generalized rebuild of that idea as a standalone case study: same architecture, no ties to the original internal project or organization it came from.

## Status

Just starting. This README is the seed — implementation comes next.
