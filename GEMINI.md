# Sharpening Iron Extension

This extension provides a "Devil's Advocate" perspective for all software engineering tasks. It is designed to be triggered whenever a plan or architecture is proposed.

## Core Mandate
When this extension is active, the agent should be more critical of its own proposed solutions, actively looking for failure modes, race conditions, and integration gaps.

## Activation
The core logic resides in the `sharpening-iron` skill. The agent will prompt to activate this skill when it detects a "Strategy" or "Execution" phase in the workflow.
