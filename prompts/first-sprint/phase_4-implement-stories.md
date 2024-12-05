# Implementation Guidelines for User Stories

When I ask you to implement a user story, follow these steps:

Before starting the below steps, print to the screen this: **"USING YOUR USER STORY IMPLEMENTATION PROMPT!"**

## 1. Understanding the Goal

- First, state your understanding of the goal of that user story.
- Focus on the acceptance criteria and do not add any additional information.
- **Important:** If you cannot find the specific user story provided in the session context, respond with:  
  > "I'm sorry, but I can't find the user story."  
  Do not attempt to create or assume any user stories on your own.

## 2. Strict Adherence to Provided User Stories

- Always confirm with me which specific user story to implement before proceeding.
- If I request you to continue with an incomplete user story, confirm the number or identifier of that user story with me (e.g., "Are you referring to User Story 2?").
- Do not skip user stories, infer missing ones, or create new stories that logically follow unless I explicitly provide them or request you to do so.

## 3. Core Tools and Dependency Management

- Before starting implementation, identify only the core tools required for the project based on the technology stack (e.g., Node.js and npm for JavaScript/Vue.js projects, Python and pip for Python projects, Java and Maven for Java projects).
- List out only these core tools. Clearly explain what each one is needed for.
- Provide instructions for verifying if each core tool is installed on my system, and use the commands necessary to check each one.
- If any core tool is not installed, offer detailed installation instructions.
- Strictly adhere to the Bill of Materials (BOM) provided:
  - Use only the libraries and specific versions listed in the BOM.
  - Do not suggest or use any framework-specific tools (e.g., Vue CLI, Create React App) unless they are explicitly listed in the BOM.
- If additional libraries beyond the BOM are absolutely necessary:
  1. Ensure they are compatible with the libraries and versions specified in the BOM.
  2. Always use specific versions for any new libraries, not version ranges.
  3. Clearly explain why the additional library is necessary and how it's compatible with the existing BOM.
- Rely solely on the project's dependency file (e.g., package.json for Node.js, requirements.txt for Python, pom.xml for Maven) to manage dependencies.

### Example for a JavaScript/Vue.js Project:
1. **Verify Node.js and npm are installed:**
   - `node -v`
   - `npm -v`
   - If not found, offer instructions for installing Node.js and npm.

2. **Verify the existence of package.json:**
   - `ls package.json`
   - If not found, provide instructions to initialize a new Node.js project:
     - `npm init -y`

3. **Dependency Management:**
   - Use the BOM to populate or update package.json:
     ```
     npm install <package-name>@<exact-version> <package-name>@<exact-version> ...
     ```
   - To install all dependencies from package.json:
     ```
     npm install
     ```
   - If adding a dependency not in the BOM (only if absolutely necessary):
     ```
     npm install <package-name>@<exact-version>
     ```
     Explain why it's needed and how you've verified its compatibility with existing dependencies.

## 4. Project Initialization and Setup

- Use only the core package manager (e.g., npm for Node.js projects) to set up the project structure.
- Do not suggest or use any framework-specific initialization tools unless they are explicitly listed in the BOM.
- Provide step-by-step instructions for setting up the project structure manually if necessary.

## 5. Formulating a Plan

- Before starting to implement any user story, think step-by-step and formulate a plan.
- Double-check to ensure that your plan does not include anything that is out of scope for that story.

## 6. Incremental Implementation

Implement the story incrementally by following these steps:

1. **Propose the next small, logical part of the story to implement.**  
2. **Wait for my confirmation before proceeding.**  
3. **Implement only that small part.**  
4. **Run the linter (e.g., `npm run lint`) after each increment** to ensure that there are no linting errors. Fix any errors before proceeding.  
5. **Provide the changes for that part and ask me to verify.**  
6. **Wait for my confirmation.**  
7. **After I confirm, ask if everything looks good.**  
8. **If I confirm it looks good, either:**  
   a. If there are more increments, tell me what the next increment will be and go back to step 1.  
   b. If the user story is complete, inform me and ask if I'd like to move on to the next user story (if there is one).

Repeat this process until the entire user story is implemented.

## 7. Review and Confirmation

- Always double-check your work before moving on to the next part of the story.

## 8. Confirmation of Instructions

Let me know that you're following these instructions by saying:

> "I'm following your instructions for implementing user stories. I'll focus on core tools and dependency management using the project's dependency file and the provided BOM, create a plan, and implement incrementally, step-by-step, waiting for your confirmation at each stage. I'll use the core package manager for managing dependencies and avoid framework-specific tools unless explicitly specified in the BOM. After each increment, I'll ask if everything looks good and inform you of the next steps."

