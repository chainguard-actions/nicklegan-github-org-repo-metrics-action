<!-- markdownlint-disable -->

# Hardening Report: nicklegan--github-org-repo-metrics-action/v2.0.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `374911c4be584df24e6da57af2d990570ef0f859`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **nicklegan--github-org-repo-metrics-action/v2.0.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### prior-fix (severity: high)

Carried forward from this version's previous harden, which fixed it; fix it again unless the code no longer has the problem. The previous harden changed action.yml without recording a finding for it, and this analysis reported nothing there. Re-apply its security changes unless the code no longer needs them. The previous patch:
```diff
diff --git a/action.yml b/action.yml
index 3cdfcb4..4930440 100644
--- a/action.yml
+++ b/action.yml
@@ -1,6 +1,5 @@
 name: GitHub Organization Repository Metrics Report Action
 description: 'A GitHub Action to generate a report that contains various metrics for all repositories belonging to a GitHub organization.'
-
 inputs:
   token:
     description: 'A Personal Access token with repo scope'
@@ -57,11 +56,10 @@ inputs:
     required: false
   installationid:
     required: false
-
 runs:
   using: 'node16'
   main: 'dist/index.js'
-
 branding:
   icon: 'list'
   color: 'blue'

```

Locations:

- `action.yml`

## Iteration Notes

### Iteration 1

**Fixes applied:** prior-fix

**Notes:**

I re-applied the previous patch to action.yml. All it did was delete three blank lines, so it changed nothing about security. This node16 action has no run steps, no uses: references, no expressions and no hardcoded credentials, so there was nothing else to fix in action.yml. I didn't check dist/index.js.

