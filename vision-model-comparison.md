# Vision Model Output Comparison: gemma-4-12b-it-qat

## Task
Compare two responses from the same vision model analyzing the same Gestalt figure-ground perception screenshot (5 dot clusters labeled "Color Set 1-5", each forming the number "20"). One response had a system prompt; one did not.

---

## Summary of Differences

| Dimension | WITH System Prompt | WITHOUT System Prompt |
|---|---|---|
| Sections | 2 (Image Description, Question Answer) | 3 (Detailed Description, Summary Explanation, Answer) |
| Redundancy | High — answer section duplicates description | Low — sections serve distinct functions |
| Analysis | Identifies Gestalt domain, stops there | Compares contrast effects across sets, explains perceptual difficulty |
| Color Set 3 | Background: muted orange/brown; Figure: bright red/coral | Background: orange/coral; Figure: tan/olive-green |
| Tone | Dry, clinical, hedging ("appears to be") | Confident, engaging ("is a visual demonstration") |
| Commentary | Suppressed by system prompt instruction | Naturally included, high value |

---

## Critical Accuracy Discrepancy

**Color Set 3 descriptions contradict each other:**

- **WITH**: "muted orange, peach, and brown dots" background; "bright red/coral dots" forming "20"
- **WITHOUT**: "most dots are orange/coral" background; "tan and olive-green dots" forming "20"

These swap which color is figure vs. ground. At least one version is factually wrong. The image was not available for verification.

---

## Verdict

**The WITHOUT-system-prompt response is better overall.**

**Reasons:**
1. Superior analytical depth — explains *why* contrast matters, not just *what* is shown
2. Less redundancy — three sections serve distinct purposes rather than duplicating content
3. Better aligned with the user's request to "fully describe AND EXPLAIN"
4. More engaging, authoritative prose style

**Caveat:** The Color Set 3 accuracy issue is unresolved and could tip the balance if the without-system-prompt version is wrong.

**System prompt effect:** The system prompt's "do not add commentary" instruction was actively harmful for this task, suppressing the interpretive analysis that made the other response valuable. The prompt design was misaligned with a question that asked for explanation.

---

## Recommendation for System Prompt Design

When the user's question asks for *explanation* (not just description), the system prompt should permit or encourage commentary. A better prompt for this use case might be:

> "Be accurate, thorough, and concise. Describe what you see, then explain its significance. For text: transcribe verbatim. For data: report exact numbers and labels."
