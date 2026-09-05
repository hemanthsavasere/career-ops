# Sponsorship salary thresholds live in user config, not system code

The Sponsorship-friendliness signal (Block A) needs to compare an advertised salary against
the EU visa floors — Germany Blue Card, Netherlands Highly Skilled Migrant, Poland Blue Card —
to judge whether an employer is likely to sponsor a senior SWE. These floors change annually
and differ in unit (DE/NL are EUR annual/monthly, PL is PLN monthly). We decided to store them
in the user-layer `config/profile.yml → sponsorship.thresholds` block with an `as_of` date per
country, and to spot-check official sources at runtime only for borderline cases. We did not
hardcode them in `scan.mjs`/`modes/`, because hardcoding would go stale within a year and
violates the "verify thresholds at runtime, never hardcode" rule already stated in
`modes/regional/eu-swe.md`.

**Considered options:** (a) runtime-verify every salary-bearing evaluation via WebSearch —
accurate but adds a WebSearch per evaluation; (b) hardcode a table in system code — no. We
chose the config table because it is cheap, user-maintainable, and carries a freshness marker
that the existing `check-table-freshness.mjs` pattern can flag.
