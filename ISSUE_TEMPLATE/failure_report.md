---
name: Model failure report
about: The detector missed, misfired, or hallucinated on an image — our most valuable contribution type
title: "[failure] "
labels: failure-report
assignees: ""
---

**This is the most useful thing you can file.** Numbers can wait; failure reports can't.

## Image context
- Source (your photo, public dataset, synthetic):
- Capture (trichoscope / dermoscope / phone macro / downloaded):
- Approx. resolution / lighting:
- One sentence on visible hair type/texture:

## What happened
- Missed units the model should have seen (count?):
- Wrong hair-count class on visible units:
- False positives (labels where there's no follicle):
- Confidence oddities (very high on wrong boxes / very low on obvious ones):

## Photo
<!--
CRITICAL: do NOT attach photos of identifiable people's scalps.
Either upload an image you own the rights to, a consented/synthetic one, or link a public
dataset image with its source URL.
-->

- Uploaded or linked:

## What you expected
<!-- e.g. "these two 4-hair bundles should have been fu3, not fu1/fu2" -->

## Severity (your gut)
- [ ] cosmetic (UI/labels)
- [ ] notable (wrong on an obvious case)
- [ ] alarming (confidently wrong on an unambiguous image)
