# Grill Me

An OMP plugin that interviews you about a loose idea until every decision is settled. It follows the grilling session from [Matt Pocock's skills](https://github.com/mattpocock/skills): questions arrive in rounds, each round is the whole frontier, and the session writes no files.

## Install

From the OMP Honk marketplace:

```sh
omp plugin marketplace add https://github.com/hhollenstain/omp-honk-marketplace.git
omp plugin install omp-grill-me-skill@omp-honk-marketplace
```

Start a new omp session, or run `/reload-plugins` in the one you already have.

## Use

Start a fresh conversation and leave plan mode off. Plan mode pushes the agent to produce a plan; this session exists to keep asking.

```text
/omp-grill-me-skill:grill-me a marketplace of small OMP skills
```

You can also invoke the skill directly:

```text
/skill:grill-me a marketplace of small OMP skills
```

`grill-me` does not start on its own. The underlying `grilling` skill is what runs the interview, including when you ask to grill an idea in prose.

Each round opens OMP's question picker through the `ask` tool. Answer that round, and the next picker is the decisions your answers just unlocked. When nothing is left, it restates the shared understanding and waits for you to confirm before doing anything else.
