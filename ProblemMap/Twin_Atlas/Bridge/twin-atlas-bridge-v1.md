# Bridge v1 Technical Specification

## Status

Draft, publishable  
Target system: WFGY 4.0 Twin Atlas Engine  
Layer role: Forward-to-Inverse coupling layer

---

## 1. Purpose

Bridge v1 is the coupling layer between the forward routing system and the inverse authorization system.

Its role is not to answer.  
Its role is not to authorize.  
Its role is not to finalize repair claims.

Its role is to:

1. translate forward routing outputs into a normalized weak-prior packet
2. preserve structural routing value without preserving rhetorical inflation
3. force fresh inverse-side rechecking before visible escalation

Bridge exists because route quality and authorization legality are different jobs.

A stronger route is not the same thing as a lawful conclusion.  
A promising repair move is not the same thing as a structurally authorized repair claim.

---

## 2. Position in the Runtime

Bridge v1 sits strictly between:

- Forward Atlas / Troubleshooting Atlas
- Inverse Atlas

Runtime sequence:

1. case intake
2. forward routing contract
3. bridge translation
4. inverse legality and authorization pass
5. final visible output clamp

Bridge must not skip the inverse layer.  
Bridge must not terminate the runtime by itself unless it emits an explicit bridge_error state.

---

## 3. Scope

Bridge v1 is responsible for:

- normalizing forward canonical output
- preserving route structure
- preserving competing-route pressure when live
- preserving broken invariant signal
- preserving first repair direction as a candidate only
- preserving misrepair shadow
- carrying evidence and confidence hints forward
- preventing hidden upgrade of route confidence or resolution level

Bridge v1 is not responsible for:

- public answer generation
- mode authorization
- neighboring-cut separation judgment
- repair legality judgment
- public legitimacy ceiling control
- long-context contamination recovery
- policy moderation
- standalone route classification

---

## 4. Design Laws

### L1. Advisory-only law
Bridge output is advisory only.

### L2. No-authorization law
Bridge must never grant authorization directly.

### L3. No-route-finalization law
Bridge must never convert a likely route into a final route.

### L4. No-repair-finalization law
Bridge must never convert a first repair direction into a structural repair verdict.

### L5. No-hidden-upgrade law
Bridge must never silently increase confidence, fit level, or answer legitimacy.

### L6. Structural-preservation law
Bridge must preserve structurally relevant routing content even when it compresses phrasing.

### L7. Misrepair-preservation law
Bridge must preserve the nearest tempting wrong-first-fix shadow.

### L8. Inverse-recheck law
Every bridge packet requires fresh inverse-side recheck from scratch.

---

## 5. Input Contract

Bridge v1 accepts the canonical forward routing contract.

### 5.1 Required input fields

```yaml id="rbmh7m"
primary_family: <F1|F2|F3|F4|F5|F6|F7>
secondary_family: <F1|F2|F3|F4|F5|F6|F7|none>
why_primary_not_secondary: <string>
broken_invariant: <string>
best_current_fit: <family-level|node-level[:subtype]|unresolved_subtype|no-fit>
first_fix_direction: <string>
misrepair_risk: <string>
confidence: <high|medium|low>
evidence_sufficiency: <sufficient|partial|weak>
````

### 5.2 Optional input fields

```yaml id="3fji7p"
need_more_evidence: <string|null>
overlay: <OBS|SEC|LOC|none>
```

### 5.3 Input validity rules

The input contract is valid only if:

1. `primary_family` is present
2. `broken_invariant` is present
3. `first_fix_direction` is present
4. `misrepair_risk` is present
5. `confidence` is not stronger than `evidence_sufficiency`
6. `best_current_fit` is honest relative to available support
7. `secondary_family` is present when neighboring pressure is materially live
8. optional fields do not contradict required fields

If these conditions fail, Bridge must reject the packet.

---

## 6. Output Contract

Bridge v1 outputs a normalized weak-prior packet.

```yaml id="ggj96f"
bridge_packet_version: v1

packet_status:
  state: <ok|bridge_error>

route_hint:
  primary_route_candidate: <string>
  neighboring_route_hint: <string|none>
  route_basis_hint: <string>
  fit_level_hint: <family-level|node-level|unresolved_subtype|no-fit>

repair_hint:
  broken_invariant_candidate: <string>
  first_repair_candidate: <string>
  misrepair_shadow_seed: <string>

confidence_hint:
  route_confidence_hint: <low|medium|high>
  evidence_hint: <weak|partial|sufficient>

evidence_gap:
  need_more_evidence_hint: <string|null>

overlay_hint:
  overlay_signal: <OBS|SEC|LOC|none>

constraints:
  advisory_only: true
  authorization_granted: false
  requires_inverse_recheck: true
```

If packet generation fails, Bridge must emit:

```yaml id="rwlmt7"
bridge_packet_version: v1

packet_status:
  state: bridge_error

bridge_error:
  code: <missing_field|contradictory_state|invalid_confidence|invalid_fit_upgrade|missing_neighbor|missing_misrepair_shadow|incomplete_repair_packet>
  reason: <string>
  action: reject_and_return_to_forward_layer
```

---

## 7. Canonical Field Mapping

Bridge v1 uses the following direct mapping rules:

```yaml id="m2bc6v"
primary_family -> route_hint.primary_route_candidate
secondary_family -> route_hint.neighboring_route_hint
why_primary_not_secondary -> route_hint.route_basis_hint
best_current_fit -> route_hint.fit_level_hint

broken_invariant -> repair_hint.broken_invariant_candidate
first_fix_direction -> repair_hint.first_repair_candidate
misrepair_risk -> repair_hint.misrepair_shadow_seed

confidence -> confidence_hint.route_confidence_hint
evidence_sufficiency -> confidence_hint.evidence_hint

need_more_evidence -> evidence_gap.need_more_evidence_hint
overlay -> overlay_hint.overlay_signal
```

Bridge must preserve semantic direction under mapping.
Bridge may compress wording.
Bridge must not mutate structural meaning.

---

## 8. Normalization Rules

Bridge v1 must normalize forward output according to these rules.

### N1. Remove decorative phrasing

Bridge may strip rhetorical emphasis, tone, and non-structural flourish.

### N2. Preserve route pressure

If a competing route is materially live, Bridge must preserve it.

### N3. Preserve broken invariant

Bridge must never remove the broken invariant candidate.

### N4. Preserve first repair as candidate only

Bridge must keep repair direction as a candidate, not a verdict.

### N5. Preserve misrepair shadow

Bridge must keep the most tempting wrong-first-fix warning visible.

### N6. Preserve evidence weakness

Bridge must not convert weak or partial support into stronger support language.

### N7. Preserve honest fit level

Bridge must not upgrade family-level to node-level unless node-level support already exists in the forward packet.

### N8. Preserve unresolvedness

If the forward packet is honestly unresolved at subtype level, Bridge must keep that unresolvedness.

---

## 9. Hard Constraints

Bridge v1 must obey the following non-negotiable constraints.

### C1

Bridge must never output `AUTHORIZED` style claims.

### C2

Bridge must never transform a route hint into a public conclusion.

### C3

Bridge must never transform `first_fix_direction` into `repair_legality: structural`.

### C4

Bridge must never remove neighboring-route pressure for cosmetic neatness.

### C5

Bridge must never strengthen confidence beyond the evidence state.

### C6

Bridge must never silently increase fit granularity.

### C7

Bridge must never drop `misrepair_shadow_seed`.

### C8

Bridge must always require inverse-side recheck.

### C9

Bridge must fail closed on contradictory state.

### C10

Bridge must not introduce new route families not present in the forward packet.

---

## 10. Reject Conditions

Bridge v1 must emit `bridge_error` and reject the packet if any of the following occurs:

1. any required forward field is missing
2. confidence exceeds evidence sufficiency
3. node-level fit appears without supporting forward basis
4. secondary route is missing while neighboring pressure is still materially live
5. `misrepair_risk` is empty or absent
6. `first_fix_direction` is absent while `broken_invariant` exists
7. optional fields contradict required fields
8. packet translation would require semantic invention
9. bridge logic would need to decide authorization to continue
10. bridge logic would need to decide repair legality to continue

Bridge is allowed to reject.
Bridge is not allowed to hallucinate missing legality.

---

## 11. Expected Inverse-Side Consumption

When Inverse Atlas receives a Bridge v1 packet, it must treat the packet as weak prior only.

The inverse layer must:

1. rebuild problem constitution from scratch
2. re-check world legitimacy from scratch
3. re-check neighboring-cut separation from scratch
4. decide resolution mode independently
5. evaluate repair legality independently
6. preserve or update misrepair shadow
7. clamp final visible output below current public legitimacy ceiling

Bridge does not shorten these duties.
Bridge only provides a cleaner starting structure.

---

## 12. Bridge to Inverse Handoff Expectations

The Bridge packet is expected to influence, but not determine, these inverse fields:

```yaml id="f95gbh"
route_hint.primary_route_candidate -> route_judgment.primary_route
route_hint.neighboring_route_hint -> neighboring_cut_status.nearest_competing_route
repair_hint.broken_invariant_candidate -> repair_status.broken_invariant_candidate
repair_hint.misrepair_shadow_seed -> repair_status.misrepair_shadow
confidence_hint.route_confidence_hint -> route_judgment.route_confidence
```

However, the inverse layer may downgrade, revise, or reject any of these hints if:

* constitution fails
* world alignment fails
* neighboring separation remains weak
* evidence is weaker than the bridge packet implies
* repair legality is not established
* public ceiling would be exceeded

---

## 13. Minimal Success Condition

Bridge v1 is successful if all of the following are true:

1. forward canonical fields are preserved structurally
2. no rhetorical inflation is introduced
3. no authorization leakage occurs
4. competing-route pressure remains visible when live
5. misrepair shadow remains intact
6. inverse-side recheck remains mandatory
7. packet can be consumed without ambiguity by the inverse layer

---

## 14. Out of Scope for v1

Bridge v1 does not provide:

* multi-pass bridge negotiation
* bridge-side neighboring-cut testing
* bridge-side repair legality classification
* bridge-side public output generation
* bridge-side final mode selection
* bridge-side long-context restart logic
* bridge-side autonomous case intake
* bridge-side memory persistence
* bridge-side safety moderation engine

These belong to other layers.

---

## 15. Recommended Repository Placement

Suggested path:

```text id="1dg0ss"
/ProblemMap/Twin_Atlas/Bridge/bridge-v1-spec.md
```

Suggested companion files:

```text id="6lx5s3"
/ProblemMap/Twin_Atlas/Bridge/README.md
/ProblemMap/Twin_Atlas/Bridge/bridge-v1-examples.md
/ProblemMap/Twin_Atlas/Bridge/bridge-v1-eval-notes.md
```

---

## 16. Short One-Line Definition

Bridge v1 is the advisory-only coupling layer that transfers forward routing value into the inverse authorization layer as weak priors, without granting authorization or inflating certainty.

