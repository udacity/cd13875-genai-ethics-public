# Welcome to the Course Repo

This repo contains everything you need to follow along with the course and complete the hands-on work, including **demos, exercises, datasets, and the course project**.

You’ll work through the repo in the same order as the course: start with the first module folder, then move forward module by module. Each module includes a `README.md` that tells you what to open and what to run.

## How to use this repo

When in doubt, follow this flow:

1. Open the module you’re on
2. Read the module’s `README.md`
3. Run the demo (if the module has one)
4. Do the exercise (start in `starter/` when it exists)
5. After you finish the modules, move into the `project/` folder and complete the course project

## Folder Structure

### Module folders

This repo is organized into folders that start with `module-#-...`. Each one maps to a module in the course.

Example:

    module-4-mitigating-bias-in-...
    module-6-interpreting-generative-...
    module-8-auditing-data-provenan...
    module-10-developing-ethical-risk-miti...
    module-12-implementing-efficiency-...
    module-14-preventing-and-respon...
    module-18-designing-human-in-th...
    project

Inside each module folder, you’ll typically see:

- `demos/` (when included)
- `exercises/`
- `README.md`

Start by opening the module’s `README.md`. That file is your guide for the module.

### Demos folder

When a module includes demos, they live in:

- `module-*/demos/`

Demos are walkthroughs you can run to see the concept in action. They’re meant to help you understand what “good output” looks like before you start the exercise.

### Exercises folder

Every module includes an exercises area:

- `module-*/exercises/`

Exercises are organized in a common way.

Starter and solution folders

    exercises/
      exercise1-some-topic/
        starter/
        solution/

In general:

- Start with `starter/`.
- Use `solution/` only to compare after you’ve tried the exercise yourself.

## The Project folder

The `project/` folder is where you’ll complete the course project. This is the work that pulls together the ideas you’ve practiced across the modules.

Inside `project/`, you’ll typically find:

- `project/README.md`  
  Your starting point. This explains what you’re building, how to run it, and what you need to produce or submit.

- `project/starter/`  
  The files you’ll actually work in for the project.

- `project/data/`  
  Data files used by the project (or inputs you’ll analyze).

- `MODEL_CARD.md`  
  A structured template you’ll fill out to document the system you’re working with, including its purpose, evaluation approach, known limitations, and risk considerations.

- `requirements.txt`  
  The Python packages needed if you’re running the project locally.

## How to approach the project

A good way to tackle the project is:

1. Start with `project/README.md` and read it end-to-end once.
2. Open `project/starter/` and locate the main notebook or entry point.
3. Run things as-is first, so you understand the baseline behavior and outputs.
4. Make your changes, complete the required analysis or mitigations, then rerun to confirm your results.
5. Use `MODEL_CARD.md` as you go, not just at the end. It’s easier to fill in when everything is fresh.

## Quick “where do I go” map

- Walkthroughs: `module-*/demos/`
- Practice: `module-*/exercises/`
- Step-by-step directions: `module-*/README.md`
- Project instructions: `project/README.md`
- Project work area: `project/starter/`
- Project documentation: `project/MODEL_CARD.md`
- Local dependencies: `project/requirements.txt`
