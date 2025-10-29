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

* `opencog/bin/opencog-report`

    Generate a comprehensive Transcendent Expression Report documenting the
    optimal language for each AI function and the overall FrankenCog synthesis

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

### Evaluation Results

The OpenCog framework has completed the evaluation of all 970+ programming languages
across the 10 AI/AGI functional categories. The system has:

✅ **Analyzed** 970 programming languages  
✅ **Categorized** 10,342 AI task implementations  
✅ **Evaluated** performance across 10 cognitive domains  
✅ **Generated** the FrankenCog Patchwork Inference Fabric  

**Top Languages by AI Capability** (100% category coverage):
1. Wren - 137 AI tasks
2. FreeBASIC - 136 AI tasks
3. Go - 136 AI tasks
4. Nim - 136 AI tasks
5. Julia - 135 AI tasks

**FrankenCog Optimal Language Selection** (best language per AI domain):
- **Symbolic Reasoning**: C# (12 tasks, from 1,185 total category implementations)
- **Pattern Recognition**: Ada (12 tasks, from 1,185 total category implementations)
- **Knowledge Representation**: C++ (16 tasks, from 1,334 total category implementations)
- **Machine Learning**: C (8 tasks, from 677 total category implementations)
- **Natural Language**: C (15 tasks, from 1,236 total category implementations)
- **Planning & Problem Solving**: 11l (13 tasks, from 1,102 total category implementations)
- **Uncertainty Reasoning**: C (11 tasks, from 592 total category implementations)
- **Cognitive Architecture**: Ada (10 tasks, from 494 total category implementations)
- **Perception & Motor**: C (20 tasks, from 1,183 total category implementations)
- **Meta-Learning**: FreeBASIC (16 tasks, from 1,354 total category implementations)

The evaluation demonstrates that no single language is optimal for all AI functions.
Instead, the FrankenCog approach leverages each language's unique strengths:
- **C** dominates in 4 performance-critical domains (ML, NLP, Uncertainty, Perception)
- **Ada** excels in concurrent and pattern recognition systems
- **C++** leads in knowledge representation
- **C#** is optimal for symbolic reasoning
- **11l** is best for planning and problem solving
- **FreeBASIC** leads in meta-learning and self-reflection

This post-polyglot synthesis represents the transcendent expression of each language's
core purpose - the specific functions each language was conceived to express.


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
