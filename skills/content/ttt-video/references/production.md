# Production outputs and records

## Review / reference

Use a compact table when helpful: source timestamp, observed speech or visual, interpretation, proposed change. For a reference creator, explain hook mechanism, information order, evidence presentation and ending; adapt those principles into original language. An apparent strong hook is an editorial judgment until analytics support a performance claim.

## Selects / repurposing

For each proposed clip provide source file, source-relative in/out, approximate duration, pillar, opening line, complete spoken copy where requested, on-screen text, relevant B-roll, proof dependency and one next action. Distinguish verbatim transcript from new voiceover. Mark timing approximate until checked against playback. Never present a new script as a quote from the footage.

Default editor handoff: opening → setup → demonstrated decision/action → takeaway → optional CTA. Choose duration from the idea and platform brief; do not force every video into a fixed length. Include framing/crop constraints, caption readability, needed pickups and audio needs only when relevant. Proposed music requires a usable license before publication. A render is complete only after a separate editor/rendering workflow actually produces and checks the output file.

Do not turn a gym clip, travel scene, account screenshot or testimonial into unsupported financial or health proof. Note redactions needed for client names, account details and private dashboards. When evidence is missing, propose a clearly labeled demonstration or a new capture.

## Evidence records

New analysis evidence IDs can use `V-<run-id>-001`; check for collisions. Record source locator, timestamp/range, modality, observation, transcript origin if applicable, and limitations in `evidence.json`. Retain original audit IDs only when actually using their source evidence. `NEW` is a capture requirement, never an evidence ID. Preserve the watch report and frame paths so observations can be traced.

## CreativeRecord export

When asked for production-ready drafts or system integration, export `creative-records.json` with these existing fields:

- `asset_id`: unique new ID; preserve existing IDs for explicit revisions.
- `type`: use the existing relevant type, e.g. talking_head, lifestyle_reel, story_sequence, b_roll_shot.
- `source_evidence_ids`: IDs actually supporting this asset.
- `hypothesis_label`: editorial hypothesis, not a measured result.
- `audience`: intended viewer.
- `pillar`: Train, Trade, Transform, or justified mix.
- `funnel_job`: intended purpose.
- `full_copy`: complete draft copy or structured frame copy.
- `proof_requirements`: what needs verification or capture.
- `media_dependencies`: files, pickups, permissions and edits needed.
- `CTA`: one action or null.
- `measurement_plan`: relevant metric and how it will be obtained; unavailable analytics remain unavailable.
- `production_owner`: confirmed owner or explicitly proposed role, otherwise null.
- `status`: draft; no automatic approved/published state.

Preserve null values with reasons in an additional `missingness` object. Add source timing and editing details in `original_record`, following the existing export approach. Write a new export by default; merge into the canonical audit only when requested. Validate JSON parsing, unique IDs, required fields, referenced evidence, and valid source-time ranges.

Useful invocation examples:

- “Use $ttt-video to review this reel's opening and give three specific changes.”
- “Use $ttt-video on these training clips and draft three Train reels with source selects and editor notes.”
- “Use $ttt-video to break down this reference's storytelling, then write an original Trade script from my journal footage.”
- “Use $ttt-video to connect these clips to the existing B-roll library and export draft CreativeRecords.”
