# OntoGEM Design Principles

OntoGEM was developed according to a set of design principles intended to promote semantic clarity, modularity, extensibility, and traceability throughout the representation of genome-scale metabolic models. These principles guided the definition of the ontology modules, classes, and relationships.

## Separation of Biological Knowledge and Model Representation

OntoGEM distinguishes biological entities and processes from their representations within a metabolic model. Biological concepts describe the underlying biological reality, whereas modeling entities describe how that knowledge is encoded in a genome-scale metabolic model.

**This separation allows multiple representations of the same biological concept, accommodates model-specific attributes, and prevents representation details from altering biological knowledge.**

## Separation of Representation and Provenance

Model representations and their provenance are modeled independently. The Modeling module captures **how** biological knowledge is represented, whereas the Provenance module captures **why** those representations were adopted.

**This distinction enables reconstruction decisions, supporting evidence, assumptions, and responsible agents to be documented without modifying the model representation itself.**

## Explicit Representation of Modeling Decisions

Modeling decisions are represented explicitly rather than being implicitly embedded in model components.

**Modeling decisions provide a common abstraction** for describing reconstruction and curation decisions, allowing their justifications, confidence assessments, provenance, and affected modeling entities to be represented in a consistent manner.

## Representation of Adopted Decisions

OntoGEM represents modeling decisions that are adopted and enacted through reconstruction or curation activities. These decisions describe how biological knowledge is incorporated into the resulting metabolic model and may be supported by explicit justifications, evidence, and assumptions.

The ontology focuses on the **adopted state of the reconstruction** rather than on exhaustively representing all hypotheses, alternatives, or intermediate interpretations considered during the reconstruction process. Alternative or rejected interpretations are therefore outside the scope of the ontology unless they are themselves adopted as modeling decisions in a subsequent reconstruction or curation activity.

This principle **establishes a clear epistemic boundary for OntoGEM** while allowing the provenance and justification of the decisions incorporated into a model to be explicitly represented.

## Explicit Representation of Scientific Justification

OntoGEM **distinguishes the reasoning that supports a modeling decision from the evidence and assumptions on which that reasoning is based**.

This separation allows scientific arguments to be represented transparently, making explicit both the available evidence and the assumptions required to interpret it.

## Modular Organization

The ontology is organized into independent but interconnected modules that represent complementary perspectives of a genome-scale metabolic model.

**This modular structure improves maintainability, facilitates future extensions, and allows individual modules to evolve** with minimal impact on the overall ontology.

## Reification of Complex Relationships

OntoGEM explicitly reifies relationships whenever they require their own identity, attributes, or provenance. Rather than representing such knowledge as simple binary relations, the ontology introduces dedicated classes to **capture the semantics of the relationship itself**.

This design supports **richer representations, improves extensibility,** and **enables relationship-specific information to be modeled independently**.

## Support for Semantic Inference

The ontology structure has been designed to support logical inference whenever appropriate. Examples include the automatic classification of proteins as enzymes based on catalytic function and the derivation of biological relationships from modeling representations.

This principle **reduces redundancy while maintaining consistency** between the Biological and Modeling modules.

## Extensibility

OntoGEM favors **extensible modeling patterns** over fixed structures. Concepts such as external records, metadata items, confidence assessments, and provenance information are represented as **independent entities, allowing new information to be incorporated without requiring changes to the ontology schema.**

## Alignment with Biological Reality

Whenever possible, OntoGEM adopts relationships and class definitions that **reflect biological reality rather than implementation details of metabolic modeling tools**.

Model-specific constructs, such as artificial reactions or reaction subsystems, are represented explicitly as modeling concepts to **preserve the distinction between biological knowledge and computational representation.**

## Practical Support for Genome-Scale Metabolic Modeling

Although OntoGEM is grounded in sound ontological principles, its primary objective is to support the reconstruction, documentation, comparison, and analysis of genome-scale metabolic models.

Consequently, modeling decisions **prioritize semantic clarity while remaining compatible with existing GEM standards, reconstruction workflows, and computational tools.**