# EU Sponsorship-Focused Senior/Staff SWE Search

This context captures the domain terms introduced for a career-ops personalization targeting
sponsorship-friendly Senior/Staff software engineering roles in Germany, the Netherlands, and
Poland. The candidate is an Indian citizen relocating from India who requires employer
sponsorship.

## Language

**Sponsorship tier**:
The classification of a job posting's sponsorship posture from the perspective of a candidate
who requires sponsorship. Values: `explicit_positive`, `inferred_friendly`, `inferred_uncertain`,
`explicit_negative`, `not_needed`.
_Avoid_: visa tier, sponsorship status (conflates with the candidate's own `visa_status`).

**Work authorization**:
The set of countries where the candidate already holds the legal right to work without
sponsorship (`location.authorized_in`). It is a property of the *candidate*.
_Avoid_: visa status, right to work.

**Sponsorship willingness**:
Whether an employer will sponsor the candidate's work permit for a role outside the candidate's
work authorization. It is a property of the *employer/posting*, and is what the Sponsorship tier
measures.
_Avoid_: sponsorship availability, "visa sponsorship" (the JD's own wording, not the concept).

**Target geography**:
The candidate's destination countries — Germany, the Netherlands, Poland — expressed in
`portals.yml` `location_filter` as full country names and major cities.
_Avoid_: target countries (ambiguous with `authorized_in`).

**Level model**:
The candidate's seniority reference: natural level is Senior/Staff; primary target is
Senior/Staff SWE; the floor is SDE-2 (Mid), accepted only when compensation is strong.
_Avoid_: "SDE-3" used alone (Amazon-specific shorthand for Senior).
