# Prompt Comparison & Evaluation

This document evaluates multiple prompt engineering strategies applied to a structured sales analytics dataset using the Gemini API.  
The goal is to assess how prompt structure, constraints, and formatting impact insight quality, hallucination risk, and business usability.

---

## Evaluation Criteria

Each prompt version is evaluated across the following dimensions:

- **Structure & Clarity** – How clearly the task is defined
- **Hallucination Risk** – Likelihood of inventing metrics or assumptions
- **Business Readiness** – Suitability for leadership consumption
- **Formatting Discipline** – Adherence to requested output format
- **Overall Effectiveness** – Practical usefulness in analytics workflows

---

## Prompt Versions Compared

### v1_unstructured
**Description:** No role, no constraints, free-form request.

- Structure & Clarity: Low  
- Hallucination Risk: High  
- Business Readiness: Low  
- Formatting Discipline: Poor  

**Observation:**  
Responses were verbose and occasionally speculative. This version demonstrates why unstructured prompts are risky for business analytics use cases.

---

### v2_role_based
**Description:** Introduces analyst role but lacks explicit constraints.

- Structure & Clarity: Medium  
- Hallucination Risk: Medium  
- Business Readiness: Medium  
- Formatting Discipline: Inconsistent  

**Observation:**  
Role conditioning improves tone but does not fully prevent assumptions or inconsistent formatting.

---

### v3_constrained
**Description:** Adds task structure and basic constraints.

- Structure & Clarity: High  
- Hallucination Risk: Low  
- Business Readiness: High  
- Formatting Discipline: Mostly consistent  

**Observation:**  
Clear improvement in relevance and factual grounding. Minor formatting deviations still observed.

---

### v4_business_safe (Best Overall)
**Description:** Strong constraints, executive framing, and explicit safety rules.

- Structure & Clarity: Excellent  
- Hallucination Risk: Very Low  
- Business Readiness: Excellent  
- Formatting Discipline: Strong  

**Observation:**  
This prompt consistently produced executive-ready insights without inventing data. Best balance of safety and usefulness.

---

### v5_format_controlled
**Description:** Enforces strict output format.

- Structure & Clarity: High  
- Hallucination Risk: Very Low  
- Business Readiness: High  
- Formatting Discipline: Excellent  

**Observation:**  
Highly reliable for dashboards and reports. Slightly rigid but ideal for automation and downstream consumption.

---

### v6_hallucination_risk
**Description:** Intentionally vague to test failure modes.

- Structure & Clarity: Low  
- Hallucination Risk: High  
- Business Readiness: Low  
- Formatting Discipline:Poor  

**Observation:**  
Frequently introduced assumptions and inferred trends not present in the data. Useful as a negative control.

---

### v7_minimal_constrained
**Description:** Minimal wording with strong implicit constraints.

- Structure & Clarity: High  
- Hallucination Risk: Low  
- Business Readiness: High  
- Formatting Discipline: Mostly consistent  

**Observation:**  
Efficient and clean. Performs well but requires careful wording to avoid ambiguity.

---

## Key Learnings

- Prompt structure and constraints significantly reduce hallucination risk.
- Explicit rules outperform role-based prompting alone.
- Format enforcement improves reliability for business reporting.
- LLMs should consume precomputed metrics rather than perform calculations.

---

## Conclusion

This experiment demonstrates that prompt engineering is a critical layer in applied GenAI analytics workflows.  
Well-designed prompts can transform LLMs from exploratory tools into reliable business insight generators when combined with verified data context.
