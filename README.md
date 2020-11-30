# plantuml_styles

A collection of PlantUML styles.

![Example Schema](/assets/db_schema_sample.png?raw=true "Example Schema")

## Motivation

For starters, I've wanted a good database schema diagramming tool for a while. I recently stumbled across these two  wonderful usages of PlantUML:

* [C4 PlantUML](https://github.com/plantuml-stdlib/C4-PlantUML)
* [Quantum Ghost's Schema Diagram gist](https://gist.github.com/QuantumGhost/0955a45383a0b6c0bc24f9654b3cb561)

## Usage

Simply add these two lines near the top of of your PlantUML file:

```
  !include https://raw.githubusercontent.com/jonathar/plantuml_styles/main/DB_Schema.puml
  LAYOUT_WITH_LEGEND()
```

Then define the schema thusly (see the samples/relational_db_scheam.puml for relations):

```
Table(user, "user\n(User in our system)") {
    pk(id) INTEGER
    not_null(unique(username)) VARCHAR[32]
    not_null(password) VARCHAR[64]
    constraints_header()
    unique_constraint(uc_user (id, username))
}
```
