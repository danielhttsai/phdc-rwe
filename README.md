# AsPEN Multi-Country RWE Program

A single-page capability site: what PHDc and the AsPEN network can deliver to support clinical
trial design and planning, with an interactive worked example.

**Live page:** https://danielhttsai.github.io/phdc-rwe/

## What is on it

- **Programme structure.** Stage 1 screens every feasible AsPEN database against the protocol;
  Stage 2 runs the protocol on the databases that survive.
- **Stage 1 demonstration.** A database feasibility matrix over five databases and eight data
  dimensions. Tick what the protocol requires and the matrix decides which databases proceed,
  which carry a caveat, and which are excluded with a reason. Requiring disease staging, for
  instance, eliminates every claims-based source before a query is written.
- **Stage 2 demonstration.** An interactive trial-eligibility funnel. Toggling a criterion
  recomputes eligible patients, one-year risk and expected events for each country. Switching
  the matrix from patients to expected events shows that the criteria costing the most patients
  are rarely the ones costing the most events.
- **Five planning questions**, answered live from whatever state the reader has set.
- **Eight service modules** across the two stages.

## Everything on the page is illustrative

The indication is fictional ("Disease X") and every figure is invented. Each retention fraction
does, however, encode a real property of the database it belongs to — Japan's NDB identifier is
derived from insurer details and breaks on a job change; Thailand's HDC sees only MOPH
facilities; a claims spine carries no routine laboratory values. The full generative model is
disclosed on the page itself, counts are rounded to three significant figures, and the print
stylesheet stamps every page with the illustrative notice.

**These numbers must never be reused as feasibility counts.** A real Stage 1 screening replaces
every fraction with a count from the actual data.

## Editing

`index.html` is a single self-contained file: no build step, no dependencies, no external
requests. The Inter variable font (latin subset) and the PHDc logo are inlined as data URIs.

To change the illustration, edit the `COUNTRIES`, `CAPS`, `CRITERIA` and `ENDPOINTS` arrays at
the top of the `<script>` block. Everything else derives from them. Scenario state is encoded in
the URL hash, so a specific configuration can be shared as a link.

The page deliberately does not use `localStorage`: every visitor must arrive at the default
scenario for the argument to land.
