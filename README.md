# Architecture2Sirius

This QVTo project performs a Model-to-model (M2M) transformation from an *".architecture"* (metamodel: architecture.ecore) model an [Eclipse Sirius](https://www.eclipse.org/sirius/) .odesign file.

## UML diagrams

```mermaid
graph LR
	model.architecture -. "«instanceof»" .-> architecture.ecore
	model.architecture -->|M2M: Architecture2Ecore| model.ecore
	model.architecture -->|M2M: Architecture2Sirius| model.odesign
	model.odesign -. "«dependsOn»" .-> model.ecore
	model.odesign -. "«dependsOn»" .-> architectureImpl.ecore
	model.ecore-. "«imports»" .-> architectureImpl.ecore
	m1.model -. "«instanceof»" .-> model.ecore
	model.odesign -. "«produces»" .-> m1.model
```