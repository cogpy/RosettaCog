RosettaCode Data Project
========================

This git repository contains (almost) all of the code samples available on
http://rosettacode.org organized by Language and Task.


## Getting the Data

All of the data is in this repository, so you can just run:

    git clone https://github.com/acmeism/RosettaCodeData

*However...*

It's a lot of data!

If you just want the latest data, the quickest thing to do is:

    git clone https://github.com/acmeism/RosettaCodeData --single-branch --depth=1


## Tools

This repository's data content is created by a Perl program called
`rosettacode`.

You can install it with this command:

    cpanm RosettaCode

You can rebuild the data with:

    make build


This repository has a `bin` directory with various tools for working with the
data.

* `rcd-api-list-all-langs`

    List all the programming language names directly from rosettacode.org

* `rcd-api-list-all-tasks`

    List all the programming task names directly from rosettacode.org

* `rcd-new-langs`

    List the RosettaCode languages not yet add to Conf

* `rcd-new-tasks`

    List the RosettaCode tasks not yet add to Conf

* `rcd-samples-per-lang`

    Show the number of code samples per language

* `rcd-samples-per-task`

    Show the number of code samples per task

* `rcd-tasks-per-lang`

    Show the number of tasks with code samples per language

* `rcd-langs-per-task`

    Show the number of languages with code samples per task


## OpenCog: AI/AGI Evaluation Framework

The `opencog` directory contains a post-polyglot transcendent evaluation framework
that analyzes all programming languages for AI and AGI capabilities. OpenCog
represents the culmination of evaluating every known programming language against
the full spectrum of AI capabilities.

### OpenCog Tools

The OpenCog framework provides tools to evaluate languages across AI domains:

* `opencog/bin/opencog-analyze`

    Analyze all languages and generate comprehensive AI capability reports
    showing which languages excel at different AI/cognitive tasks

* `opencog/bin/opencog-manifest`

    Generate the FrankenCog Integration Manifest - identifies the optimal
    language for each AI function to create a "patchwork" of best implementations

* `opencog/bin/opencog-eval-lang <language>`

    Evaluate a specific language's AI capabilities in detail

* `opencog/bin/opencog-eval-category <category>`

    Evaluate all languages for a specific AI category (e.g., symbolic_reasoning,
    machine_learning, natural_language, etc.)

### AI Categories

OpenCog categorizes tasks into these AI/cognitive domains:

- **Symbolic Reasoning**: Logic, theorem proving, constraint satisfaction
- **Pattern Recognition**: Search, matching, classification
- **Knowledge Representation**: Data structures, graphs, semantic networks
- **Machine Learning**: Statistical methods, optimization, neural networks
- **Natural Language Processing**: Text analysis, parsing, NLP
- **Planning & Problem Solving**: Heuristic search, game playing, puzzles
- **Uncertainty Reasoning**: Probabilistic methods, fuzzy logic
- **Cognitive Architecture**: Concurrent systems, agent-based systems
- **Perception & Motor**: Image processing, signal processing
- **Meta-Learning**: Self-improvement, reflection, code generation

See `opencog/README.md` for complete documentation.


## To Do

Pull requests welcome!

This project is not a perfect representation of RosettaCode yet.
It has a few uncicode issues.
It also has to deal with various formatting mistakes in the mediawiki source
pages.

* Fix bugs

* Correct the 100s of guessed file extensions in `Conf/lang.yaml`

* Ability to only fetch cache pages since last pushed data update

* Support names with non-ascii characters

* Add more bin tools

* Address errors reported in rosettacode.log after running `make build`
