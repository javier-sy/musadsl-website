---
anchor: getting-started
title: Getting Started
menu: Getting Started
order: 40
class: getting-started
content_class: install-steps
---
{:ext: target="_blank" rel="noopener"}

### Recommended Editor

#### RubyMine

RubyMine provides the best experience for MusaDSL development &mdash; intelligent autocomplete
of methods and parameters, hover documentation, and type inference help you discover the API
as you code.

**Free licenses available:**

- [Non-commercial use](https://www.jetbrains.com/non-commercial/){:ext} &mdash; for learning, hobbies, open-source, content creation
- [Students](https://www.jetbrains.com/academy/student-pack/){:ext} and [Teachers/Researchers](https://www.jetbrains.com/academy/teacher-pack/){:ext} &mdash; with institutional email

Download on: [jetbrains.com/ruby](https://www.jetbrains.com/ruby/){:ext}

#### Visual Studio Code

VSCode with the Ruby LSP extension also works well, though Ruby autocomplete and hover
documentation are less complete than in RubyMine.

Download on: [code.visualstudio.com](https://code.visualstudio.com/){:ext}

### Framework Installation

**Requirements:** [Ruby 3.4+](https://www.ruby-lang.org/){:ext}

Install the core Musa-DSL gem:

    gem install musa-dsl

### Documentation

For detailed documentation, see the README and API docs of each project:

{% include link-table.html table="documentation" %}

### Demo Projects

A comprehensive collection of **20+ working examples** demonstrating
MusaDSL capabilities, from basic setup to advanced multi-phase compositions:

- **Basic concepts**: Setup, series, neumas, canon
- **Generative tools**: Markov, Variatio, Darwin, Grammar, Matrix
- **DAW integration**: MIDI sync, live coding, clock modes
- **External protocols**: OSC with SuperCollider and Max/MSP
- **Advanced patterns**: Event architecture, parameter automation, multi-phase compositions

Each demo is a complete, runnable project with documentation explaining the concepts demonstrated.

[<ion-icon name="logo-github"></ion-icon> musadsl-demo Repository](https://github.com/javier-sy/musadsl-demo){:ext}
