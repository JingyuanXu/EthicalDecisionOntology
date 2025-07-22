## Basic Version (corresponds to published chapter)

- Uses SWRL rules with numeric comparisons (`swrlb:lessThanOrEqual`, etc.) 

- Defines input scores as data properties

- Executable with Protégé + Pellet

- A minimal baseline version where fuzzy categories are defined only through SWRL rule conditions, with no fuzzy class modeling in OWL.



## Advanced OWL Version (Optional Extension)

- Models fuzzy categories (e.g., `MediumFairnessDecision`) using `owl:intersectionOf`

- Represents semantic threshold logic within the ontology

- Not used in the chapter directly, but useful for symbolic-fuzzy hybrid reasoning



## Software Requirements

- **Protégé**: Version 5.6.1 or later  
- **Reasoner**: Pellet (for SWRL built-in support)  
- **Java Runtime**: JDK 8 or newer

---

## Reproduction Steps

1. Open the file `EquationsAndRules.rdf` in Protégé (v5.6.1 or later).  
   This file contains the full ontology, SWRL rules, and the test individuals.

2. Ensure the "SWRL Rules" tab is enabled (Window → Tabs → SWRL Rules).  
   You can view the logic rules under this tab.

3. In the top menu, go to `Reasoner → Pellet` and select `Start reasoner`.

4. Once reasoning is complete, go to the "Individuals" tab and select D1, D2, or D3.

5. In the “Types (inferred)” panel, verify the classification:
   - D1 → `UnacceptableDecision`
   - D3 → `HighAcceptabilityDecision`
   - D2 → no classification (ambiguous case)

---

## Notes

- If you wish to re-enter the rules manually, you can start from `EthicalDecisionOntology.owl` and input the SWRL rules using the SWRL tab.
- `EquationsAndRules.rdf` is the fully saved version after rules were entered and can be used directly for reproducibility.
- `SWRL_Only_Baseline.rdf` provides a simplified baseline version of the ethical reasoning framework, in which fuzzy category thresholds are encoded entirely within SWRL rules rather than using overlapping OWL class definitions. This configuration removes fuzzy class axioms and relies only on rule-based logic to classify decisions based on numerical thresholds.
- All logic is encoded using standard OWL 2 + SWRL constructs.



