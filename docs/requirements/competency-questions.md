
# Competency Questions

The table below lists the competency questions defined to describe the functional requirements of OntoGEM. The questions cover the provenance, representation, unification, and validation of knowledge involved in the reconstruction and curation of genome-scale metabolic models.

* **Topic** - refers to the subject addressed by the question.
* **Explanation Type** - refers to the classification of the question according to the [Explanation Ontology](#note-about-explanation-ontology).

The competency questions are used to guide the development of OntoGEM and to assess whether the ontology provides the concepts and relationships required to represent the knowledge necessary to answer them.

| # | Competency Question | Topic | Explanation Type |
|:-:| --- | :--- | :--- |
| 1 | Which validation checks has the model passed? | Provenance - Model | Safety and Performance |
| 2 | Which databases were used in this reconstruction? | Provenance - Model | Data |
| 3 | Which tools were used during the reconstruction? | Provenance - Model | Trace Based |
| 4 | Which model elements were manually curated vs automatically generated? | Provenance - Model | Data |
| 5 | Which modeling decisions in model M lack experimental validation? | Provenance - Model | Scientific |
| 6 | What proportion of the model is supported only by computational evidence? | Provenance - Model | Statistical |
| 7 | How was this modeling decision established (experimentally validated, inferred by the curator, or automatically generated)? | Provenance - Model | Trace Based |
| 8 | Which reactions currently included in the model are not backed by any biological or literature evidence? | Provenance - Reaction | Scientific |
| 9 | Which reactions were added only by computational gap-filling? | Provenance - Reaction | Trace Based |
| 10 | From which source(s) (e.g., database or literature) was reaction R derived? | Provenance - Reaction | Data |
| 11 | Is there evidence from biology or the literature that supports including this reaction in the model? | Provenance - Reaction | Scientific |
| 12 | Which reactions are considered reversible only due to modeling assumptions? | Provenance - Reaction | Rationale |
| 13 | What evidence supports the gene-protein-reaction (GPR) rule of reaction R? | Provenance - GPR | Scientific |
| 14 | Who curated the GPR associations? | Provenance - GPR | Responsibility |
| 15 | Was the chemical formula of metabolite M verified manually, computationally, or both? | Provenance - Metabolite | Trace Based |
| 16 | What alternative representations exist for this metabolite, and from which sources? | Data - Metabolite | Data |
| 17 | Which metabolites lack links to external database identifiers? | Data - Metabolite | Data |
| 18 | Which external database identifiers are linked to metabolite M? | Data - Metabolite | Data |
| 19 | What alternative representations exist for this reaction, and from which sources? | Data - Reaction | Data |
| 20 | Which reactions lack links to external database identifiers? | Data - Reaction | Data |
| 21 | Which external database identifiers are linked to reaction R? | Data - Reaction | Data |
| 22 | What type of reaction is reaction R (e.g., metabolic, transport, exchange, biomass, or artificial)? | Data - Reaction | Structural |
| 23 | Which reactions produce metabolite M? | Data - Reaction | Structural |
| 24 | Which reactions consume metabolite M? | Data - Reaction | Structural |
| 25 | Are all enzymatic reactions associated with at least one valid GPR rule? | Data - Reaction | Safety and Performance |
| 26 | What are the substrates of the reaction R? | Data - Reaction | Structural |
| 27 | What are the products of the reaction R? | Data - Reaction | Structural |
| 28 | Do metabolite representations M1 and M2 correspond to the same metabolite? | Data unification | Contrastive |
| 29 | Do reaction representations R1 and R2 correspond to the same reaction? | Data unification | Contrastive |
| 30 | Which attributes from different sources are in conflict (e.g., stoichiometry, charge, or reaction directionality)? | Data unification | Data |
| 31 | Which modeling assumptions justify the reaction bounds assigned in model M? | Modeling decision | Rationale |
| 32 | Under which modeling assumptions is this metabolite or reaction representation valid? | Modeling decision | Contextual |
| 33 | For which organism(s) is reaction R intended? | Data - Model | Contextual |
| 34 | Does this metabolite represent a specific chemical entity or a generic class? | Data - Model | Structural |
| 35 | How many dead-end metabolites are in the model? | Data - Model | Statistical |
| 36 | How many blocked reactions are in the model? | Data - Model | Statistical |
| 37 | Are all the reactions in the model mass-balanced? | Data - Model | Safety and Performance |
| 38 | Are all the reactions in the model charge-balanced? | Data - Model | Safety and Performance |
| 39 | Does the model contain energy-generating cycles? | Data - Model | Safety and Performance |
| 40 | Does the model contain mass-generating cycles? | Data - Model | Safety and Performance |
| 41 | Is the model stoichiometrically consistent? | Data - Model | Safety and Performance |
| 42 | Which metabolites need to be consumed but are not produced in the model? | Data - Model | Structural |
| 43 | Which genes can be knocked out to block the production of metabolite M? | Data - Model | Simulation Based |
| 44 | Does the model achieve a MEMOTE score above a specified threshold? | Data - Model | Safety and Performance |



## Note about Explanation Ontology

[Explanation Ontology (EO)](https://tetherless-world.github.io/explanation-ontology/) is an ontology developed to represent different types of explanations in AI systems.

Although OntoGEM does not adopt EO as an ontology, we adopted its classification of explanation types to categorize the competency questions designed for OntoGEM. This classification is used to indicate the type of explanation that can be provided by answering each competency question.

Some competency questions do not provide an explanation in the sense defined by EO. Instead, they retrieve structural information about the model and its entities. For these cases, we introduced an additional category, **"Structural"**, which is not part of the EO classification.

A summary of the meaning of each explanation type used in this classification is provided in the table below.

| Explanation Type | Brief Description |
| --- | --- |
| **Scientific** | Explains assertions or model elements using scientific evidence, publications, experiments, or other literature-based support. |
| **Trace Based** | Explains how a result was produced by exposing the sequence of computational or curation activities involved. |
| **Rationale** | Explains the reasoning, assumptions, or considerations behind a modeling decision or assertion. |
| **Contextual** | Explains how environmental, biological, or modeling context influences an assertion, decision, or formulation. |
| **Data** | Explains which data sources were used, how they were integrated, and whether information was curated, inferred, or automatically generated. |
| **Responsibility** | Explains who created, curated, validated, or is otherwise responsible for a given model element or decision. |
| **Safety and Performance** | Explains the validation status, robustness, reliability, or performance of a model or model element. |
| **Statistical** | Explains model characteristics or conclusions using quantitative summaries, proportions, measurements, or other numerical evidence. |
| **Contrastive** | Explains why one formulation, representation, or decision was chosen instead of an alternative. |
| **Case Based** | Explains assertions or decisions by analogy with similar prior cases or previously curated examples. |
| **Counterfactual** | Explains what would change under different assumptions, parameters, or conditions. |
| **Simulation Based** | Explains expected outcomes through simulated or hypothetical execution scenarios. |
| **Everyday** | Explains concepts using intuitive, domain-accessible language based on common understanding. |
| **Impact** | Explains the consequences or downstream effects of a modeling decision, assertion, or recommendation. |
| **Fairness** | Explains how bias, imbalance, or unequal treatment is addressed in the modeling process. |
| **Structural (not included in EO)** | Provides structural information about the organization and relationships among model entities, such as reaction participants, classifications, connectivity, and biological associations, without primarily addressing provenance, evidence, or reasoning. |

