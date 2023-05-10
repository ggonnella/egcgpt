# EGC-GPT

This directory contains prompts for attempting automatic extraction, using GPT
large language models, of rules about the contents of genomes of prokaryotic
organisms from scientific literature.

## Modules

The modules directory contains collection of modules, i.e. different
way to formulate the same concepts (e.g. more or less verbose).

## Prompt configuration files

The prompts directory contains collection of prompt configuration files,
YAML files, which express a prompt as combination of entries from module files.

Paths of the module files are written relative to the main directory of the
repository.

## Script for combining text modules

The scripts directory contains the script ``combine_text_modules.py``,
which is employed for combining small snippets of text
(here called modules) into a complete text.

The script takes as an argument the prompt configuration file and outputs
a prompt, which can be passed to GPT.
Since paths in the prompt configuration files are written as relative to
the main directory of the repository, the way to create a prompt is:
```
cd egcgpt # main directory of the repository
scripts/combine_text_modules.py prompts/FILENAME
```
where FILENAME is the name of the prompt configuration file.

## Acknowledgements

This rule collection has been created in context of the DFG project GO 3192/1-1
“Automated characterization of microbial genomes and metagenomes by collection
and verification of association rules”. The funders had no role in study
design, data collection and analysis.

