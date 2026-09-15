# AAG Fork Handoff — flutter_inappwebview

## Why this repository exists

This repository is a **fork used for an upstream Linux WebView contribution**, not an AAG-owned replacement distribution of flutter_inappwebview. Upstream source, documentation and licensing remain authoritative.

## AAG contribution context

The fork was used while diagnosing Otzaria Linux WebView behavior. The coordinated fix addressed Linux rendering/fallback behavior needed by the real Otzaria application, including the black-surface/plugin-rendering failure mode and touch-related acceptance at the application layer. The lower-level contribution is tracked in upstream pull request **Otzaria/flutter_inappwebview#21** and is paired with the application-level **Otzaria/otzaria#1261** work.

## Engineering boundary

A lower-level WebView patch should be justified by a minimal engine/plugin behavior problem, not by Otzaria-specific UI assumptions. Keep application-specific policy in the Otzaria repository. When testing this fork, validate both a focused WebView reproduction where possible and the real Otzaria Linux package that originally exposed the problem.

## Fork workflow

Before further changes, fetch upstream and check whether PR #21 has been merged, superseded or needs rebasing. Keep commits narrowly scoped for review. Avoid unrelated formatting/vendor churn. Preserve upstream compatibility and document any Linux-specific fallback behavior clearly.

## Acceptance expectations

For changes in this area, verify successful WebView creation/rendering, absence of the prior black surface, plugin/content rendering, touch/event behavior relevant to the consuming application, fallback behavior when the preferred EGL/zero-copy path is unavailable, and no obvious regression on supported non-Linux paths that CI can exercise.

## Historical integrity rule

Do not present this fork as a separate AAG product. Its purpose is to carry/test an upstreamable fix. If upstream accepts the change, synchronize the fork and retire unnecessary divergence.

## Current status

As of the 2026-09-15 portfolio documentation audit, the fork remains part of the coordinated Otzaria Linux upstream contribution. Upstream PR discussion is the authoritative review/status record.