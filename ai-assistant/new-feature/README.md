# Post-Scaffolding Sprint Workflow Chain: AI-Assisted Planning and Implementation

## Overview

**Note: This workflow is designed for projects that have already completed their initial scaffolding (Sprint 1). It assumes basic project structure, initial dependencies, and core technologies are already in place.**

Below is a visual representation of the workflow (simplified for brevity). Also each phase has an associated prompt to guide the developer through that phase (i.e. phase = prompt).

![Post-Scaffolding Sprint Workflow Chain](post-scaffolding-sprint-workflow.png)

This workflow represents a chained sequence of AI-assisted processes for planning and implementing new features. Each phase produces specific outputs that become required inputs for subsequent phases, creating a connected chain of development activities.

The workflow operates through four sequential phases:

```
Phase 1: Implementation Status Analysis
↓ [Outputs feed Phase 2]
Phase 2: Sprint Story Generation
↓ [Outputs feed Phase 3]
Phase 3: Story Analysis
↓ [Outputs feed Phase 4A]
Phase 4A: Story Steps Implementation
↓ [Outputs feed Phase 4B]
Phase 4B: Unit Testing
```

## Input/Output Chain

### Phase 1: Implementation Status Analysis (`#analyze-impl`)

[Implementation Analysis Prompt](step_1-analyze-impl.md)

#### Purpose

Assess current project state, identify implemented and pending features

**Initial Inputs Required:**

- Project requirements list
- Previous sprint's user stories
- Core technology stack (e.g., package.json, pom.xml, requirements.txt)

**Key Outputs → [Feed into Phase 2]:**

- Implementation Status Report (`implementation_status.md`)

### Phase 2: Sprint Story Generation (`#generate-sprint-stories`)

[Sprint Story Generation Prompt](step_2-generate-sprint-stories.md)

#### Purpose

Create focused user stories for the next sprint based on technical dependencies

**Required Inputs (including Phase 1 outputs):**

- Implementation Status Report
- Previous sprint's user stories

**Key Outputs → [Feed into Phase 3]:**

- Sprint Stories (`sprint_X_stories.md`)

### Phase 3: Story Analysis (`#analyze-story S<X.Y>`)

[Story Analysis Prompt](../shared/analyze-story.md)

#### Purpose

Break down user stories into atomic, implementable functional steps

**Initial Inputs Required:**

- Sprint story for S<X.Y>

**Key Outputs → [Feed into Phase 4A]:**

- Story Steps Report (`S<X.Y>-story-steps.md`)

### Phase 4A: Story Steps Implementation (`#implement-step S<X.Y> [step-number]`)

[Implementation Prompt](../shared/implement-step.md)

#### Purpose

Systematically implement one specific step from the story analysis, ensuring all requirements are met using only approved dependencies.

**Key Outputs → [Feed into Phase 4B]:**

- Code changes implementing the specified step

**Iteration Note:**
Phases 4A and 4B iterate until all steps for a user story have been implemented and unit tested.

### Phase 4B: Story Steps Unit Testing (`#generate-tests S<X.Y> [step-number]`)

[Unit Test Generation Prompt](../shared/generate-tests.md)

#### Purpose

Generate and verify unit tests for the implemented story step, ensuring comprehensive test coverage.

**Required Inputs (including Phase 3 outputs):**

- Story Steps Report (`S<X.Y>-story-steps.md`)
- Sprint story
- Project's dependency definition file (e.g., package.json)

**Key Outputs:**

- Unit tests for the implemented step
- Test results indicating pass/fail status

## Workflow Chain Execution

### Starting the Chain

1. **Initiate Implementation Analysis:**

   ```
   #analyze-impl
   ```

   - Ensure all Phase 1 inputs are available
   - Wait for complete analysis before proceeding

2. **Generate Stories:**

   ```
   #generate-sprint-stories
   ```

   - Must have all Phase 1 outputs available
   - Proceeds only when analysis outputs are complete

3. **Analyze Story:**

   ```
   #analyze-story S<X.Y>
   ```

   - Ensure the specific user story is available in the context
   - Wait for story analysis to complete before proceeding

4. **Implement Stories, step by step:**
   ```
   #implement-step S<X.Y> [step-number]
   ```
   - Requires complete story analysis outputs
   - Execute for each story and step, in sequence

### Progress Tracking

Monitor chain progress using status commands:

```
#analyze-impl-status
#generate-sprint-stories-status
#analyze-story-status
#implementation-status
```

### Chain Dependencies

```
Implementation Status Analysis
└── Outputs required for Story Generation:
    ├── Implementation Status Report
    ├── Previous sprint's user stories
    └── Story Generation
        └── Outputs required for Story Analysis:
            ├── Sprint Stories (sprint_X_stories.md)
            └── Story Analysis
                └── Outputs required for Story Implementation:
                    ├── Story Steps Report (S<X.Y>-story-steps.md)
                    ├── Sprint story
                    └── Project's dependency definition file (e.g., package.json)
                        └── Outputs required for Story Implementation:
                            ├── Code changes implementing the specified step
                            └── Story Steps Report (S<X.Y>-story-steps.md)
                                └── Outputs required for Unit Testing:
                                    ├── Unit tests for the implemented step
                                    └── Test results indicating pass/fail status
```

## Maintaining Chain Integrity

### Verification Points

Each phase has specific verification points where the chain integrity must be confirmed:

1. **Analysis → Story Generation**

   - Verify implementation status report is complete
   - Confirm previous sprint stories are available

2. **Story Generation → Story Analysis**

   - Verify all sprint stories have required components

3. **Story Analysis → Implementation**
   - Verify story steps report is complete
   - Confirm dependency definition file is available

### Chain Break Prevention

To maintain workflow integrity:

1. Never skip phases or assume outputs
2. Verify all outputs before proceeding to next phase
3. Keep all documentation updated as you progress
4. Use status commands to confirm current state
5. Don't proceed if required inputs are missing

## Best Practices for Chain Execution

1. **Document Management**

   - Keep all phase outputs in accessible locations
   - Document any modifications to outputs
   - Version control all artifacts

2. **Phase Transitions**

   - Explicitly verify all required outputs exist
   - Validate output quality before proceeding
   - Document any assumptions or decisions

3. **Dependency Handling**
   - Track both technical and workflow dependencies
   - Verify dependency satisfaction at each step
   - Document any dependency changes

## Using the Workflow Chain

1. **Preparation**

   - Gather all initial inputs
   - Verify input completeness
   - Set up documentation structure

2. **Execution**

   - Follow the chain sequence strictly
   - Verify outputs at each step
   - Maintain documentation of progress

3. **Verification**
   - Use status commands frequently
   - Verify chain integrity at each phase
   - Document completion of each phase

## AI Integration Notes

This workflow chain has been tested with different LLMs:

- AI Assistant: aider
- Implementation Prompt: Claude 3.5 Sonnet (October 22, 2024 release)
- Other Workflow Prompts: Claude 3.5 Haiku (October 22, 2024 release)

The chain assumes:

- AI can handle file operations
- Developer verifies all outputs
- Each phase completes fully before chain proceeds

## Chain Verification

Before starting each phase, verify:

1. All required inputs are available
2. Previous phase outputs are complete
3. All dependencies are satisfied
4. Documentation is current

Remember: The strength of this workflow lies in its chained nature. Each phase builds upon the outputs of the previous phase, creating a comprehensive and connected development process.
