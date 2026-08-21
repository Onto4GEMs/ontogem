## Attributes

The table below lists the attributes defined in OntoGEM.

- **Attribute** - the preferred label of the attribute.
- **Domain** - the class whose instances may have the attribute.
- **Datatype** - the datatype of the attribute value.
- **Required** - indicates whether the attribute is required for instances of the specified domain class.
- **Definition** - describes the meaning of the attribute.
- **Notes** - provides additional information about the attribute, including modeling considerations, constraints, or implementation details.

| **Attribute** | **Domain** | **Datatype** | **Required** | **Definition** | **Notes** |
|---|---|---|---|---|---|
| **scientific name** | *target organism* | `string` | yes | Accepted scientific name of the organism. | Primary biological designation. |
| **strain** | *target organism* | `string` | no | Strain or isolate designation of the organism. | Particularly relevant for microorganisms. |
| **ec number** | *catalytic function* | `string` | no | Enzyme Commission classification assigned to the catalytic function. | Describes the function rather than the enzyme itself. |
| **name** | *metabolic pathway* | `string` | yes | Human-readable name of the metabolic pathway. | Metabolic pathway needs a separate name because it does not have a 1:1 relationship with any class in the modeling module. |
| **model identifier** | *metabolic model, model element representation* | `string` | yes | Identifier assigned to a model or model element within a metabolic model. | Distinct from ontology IRI. Sometimes curators use the same identifier from external databases, for example, from MetaNetX or BiGG. This attribute is intended to represent this kind of ID. |
| **description** | *metabolic model, model element representation* | `string` | no | Textual description providing additional information about a modeling entity. | |
| **version** | *metabolic model* | `string` | no | Version of the metabolic model. | Useful for model evolution. |
| **chemical formula** | *metabolite representation* | `string` | yes | Chemical formula associated with the represented metabolite. | |
| **charge** | *metabolite representation* | `integer` | yes | Net electrical charge of the represented metabolite. | |
| **lower bound** | *reaction representation* | `number` | yes | Minimum allowable flux through the represented reaction. | Core FBA parameter. |
| **upper bound** | *reaction representation* | `number` | yes | Maximum allowable flux through the represented reaction. | Core FBA parameter. |
| **objective coefficient** | *reaction representation* | `number` | no | Coefficient of the represented reaction in the objective function. | Default: 0. Required for linear objective definition. |
| **abbreviation** | *compartment representation* | `string` | no | Short abbreviation of the represented compartment. | Optional if the identifier already fulfills this role. |
| **role** | *reaction participation* | `string` | yes | Role of a metabolite representation as a substrate or product in a reaction representation. | Restricted to substrate and product in the current scope. It can probably be inferred from stoichiometric coefficients. |
| **stoichiometric coefficient** | *reaction participation* | `number` | yes | Stoichiometric coefficient associated with the participation of a metabolite representation in a reaction representation. | Fundamental quantitative property of reaction participation. |
| **title** | *agent, activity, evaluation result, modeling decision, justification, evidence, assumption, information source* | `string` | yes | Human-readable designation assigned to an entity. | Provides a concise label for identifying an individual, e.g., "Manual Curation #2" or "MEMOTE Evaluation #1". |
| **description** | *agent, activity, evaluation result, modeling decision, justification, evidence, assumption, information source* | `string` | no | Textual description providing additional information about an entity. | Used when information beyond the title is needed to describe the entity. |
| **date** | *activity* | `date` | yes | Date on which the activity was ended. | If recording start/end is important, we can consider using `prov:startedAtTime` and `prov:endedAtTime`. |
| **confidence score** | *modeling decision* | `integer` | no | Numerical assessment of the confidence associated with a modeling decision according to the confidence scoring system of Thiele and Palsson. | The score is currently represented according to the established scoring system. The value may potentially be inferred in future work. |
| **url** | *information source* | `URI` | no | A Uniform Resource Locator that provides access to the information source. | Useful for information sources that are accessible online, such as databases and publications. |
| **version** | *software agent* | `string` | no | Version identifier of the software agent involved in the activity. | |
| **score** | *evaluation result* | `decimal` | no | Numerical value produced by an evaluation activity according to the evaluation method used. | Useful for MEMOTE scores and other quantitative evaluation results. Optional in case the evaluation criterion is boolean. |
| **pass status** | *evaluation result* | `boolean` | no | Indicates whether the evaluated entity satisfies the evaluation criterion according to the evaluation method. | Optional because not every evaluation necessarily has a binary pass/fail outcome. |