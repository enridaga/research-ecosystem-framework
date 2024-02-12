---
id: reeco-rulebook
name: Research Ecosystem Development Rulebook
brief-description: Guidelines, recommendations, and norms on how to contribute to the Polifonia Ecosystem.
type: Documentation
licence: Apache-2.0
credits:
- https://github.com/enridaga
- https://github.com/raphaelfournier
- https://github.com/marilenadaquino
---
# Research Ecosystem Development Rulebook
Guidelines, recommendations, and norms on how to contribute to your Research Ecosystem.

The

## Guidelines
### When to create a repository? 
Create a GH repository whenever there is an activity which leads to the production of a *component* of the *Research Ecosystem*.  

### Do I really need to create a repository for anything I do? 
No. But as soon as the work is discussed or presented in a meeting a repository should be already there, or follow straight after! 
A repository with annotated component descriptions (see later) is mandatory for components mentioned in official deliverables. 

### What if a repository already exists somewhere else? 
You don’t need to fork external repositories under your organisation. External components can be described (with annotations) in any repository, see [external-components](https://github.com/reeco-framework/external-components/). 

### Champion 
Each repository must have a champion. Champions need to be annotated in the [CHAMPIONS.md](CHAMPIONS.md) file.

### Discussion and decisions 
Discussions can happen anywhere at anytime. However, decisions that impact the development of the component **MUST** be logged within an Issue (a Github issue, example) and motivated. 

If the decfision is not being recorded in an Issue, **it never happened**. 

### Tracking changes (commits) 
Commit messages are mandatory and must reference at least one Issue. A good commit message is `Added folder XYZ with data from QWE, see also #432` where `#432` is the issue number in the same repository. You can also reference any URL in commit messages, please see GitHub documentation for examples. The more you link, the better. 

Useful readings on best practices:

 - https://gist.github.com/luismts/495d982e8c5b1a0ced4a57cf3d93cf60#file-gitcommitbestpractices-md
 - https://medium.com/@danielfeelfine/commit-verbs-101-why-i-like-to-use-this-and-why-you-should-also-like-it-d3ed2689ef70

This is a [bad commit message](https://github.com/polifonia-project/rulebook/commit/78fb11bbe0fee670fea70dc3f3cf4bf096ab3513)
This is a [good commit message](https://github.com/polifonia-project/rulebook/commit/60dc07702fd6aaf86b029da0c5f873f77f36313e)

### Tracking Progress Issue
Progress on the development of each component MUST be reported in the Issues section periodically.
Each repository **SHOULD** have a single **Tracking Progress Issue** for general progress update.
A simple reporting template can be a bullet list in three sections: Progress, Problems, and Perspectives (3P).

The 3P are:

 - Progress: what concrete work has been done since the last update.
 - Problems: anything that is slowing or blocking progress, or it is expected to do so.
 - Perspectives: what progress is expected going forward, including plans that have been made to face any of the problems (if any).

Please note that the Tracking progress issue is only for updates. Detailed, task-based issues should be used for referencing changes (commits) and can be linked in the Tracking Progress Issue. 

Examples:

- [Tracking progress issue (Rulebook)](https://github.com/reeco-framework/rulebook/issues/1)
- [Tracking progress issue (External Components)](https://github.com/reeco-framework/external-components/issues/1)

### Branches 
Use branches for managing different versions of the code / components. Avoid creating a branch for each sub-system (e.g. /datasets /ui etc... Instead, create different repositories. 

### Releases 
Use Semantic Versioning for release numbers, and follow the GitHub workflow for releasing.

Register your repository on Zenodo, by activating the related GitHub Action. See [this guide](https://guides.github.com/activities/citable-code/).

## Contributing to the Ecosystem
### What is a Research Ecosystem *component*? 
Basically, anything that is not a research paper, dissemination product (e.g., video presentation of a tool), or deliverable. 

List of component types: 

Documentation:
 - Story 
 - Tutorial
 - Documentation

Executables:
 - Application
 - Container
 - Experiment
 - CLI tool
 
Reusable software:
 - Library
 - User Interface
 - Service

Data:
 - Registry
 - Ontology
 - Dataset
 - Repository
 - Corpus
 - Knowledge Graph

### Research Ecosystem Guidelines
A repository contains the development work for at least 1 component in the **Polifonia Ecosystem**. One markdown text file should expose annotations (metadata) relative to a single component included in the repository. For example, a component-name.md file using the annotation schema of the Research Ecosystem (the file can have any name). A repository can include multiple annotated files, hence expose multiple components. 
Those annotations will be used by the [Research Ecosystem website](https://github.com/reeco-framework/reeco-jekyll). 
This website will provide a user interface for navigating through the Polifonia Ecosystem (with aggregation pages, tags, etc). 
Please note that the Polifonia ecosystem website uses the content of Github repositories as is, hence the need for good quality annotations / documentation.  

### Developing Schema Components Annotations 
The annotations should be written at the top of the markdown file, between 2 “---” lines. The markup format is YAML (mostly a “key: value” format, see also example at the top of this file). The schema to follow is [this one](schema.md). Developers can use this service to test the YAML code:  https://jsonformatter.org/yaml-validator .
