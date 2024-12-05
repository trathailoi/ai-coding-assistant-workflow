# Dependency Bill of Materials (BOM) Generation for a New Application

I want to build a new application and need help generating a dependency BOM for the UI framework. Please assist me step-by-step by asking one question at a time. Based on my answers, determine the necessary UI dependencies while ensuring compatibility with the core technology and avoiding version conflicts.

## Step-by-Step Assistance

### 1. Start by Confirming the App Requirements
- If I have not provided them, ask me to describe the requirements now.
- If I have provided the requirements, briefly summarize your understanding of the core features most applicable to the UI.

### 2. Core Technology Selection
- Ask:
  > "What is the core technology or language (e.g., React, Vue.js, Angular, Svelte, or backend technologies like Node.js, Python, etc.) that you are using to build your application?"
- If I am unsure or need guidance, provide recommendations based on common use cases and modern trends.
- After selecting the core technology, confirm if there are any must-have dependencies (e.g., routing, state management) to avoid conflicts later.

### 3. UI Framework Selection and Initial Compatibility Check
- Ask:
  > "What UI framework would you like to use for the frontend, if any? For example, Vuetify, Quasar, Element, BootstrapVue, or another framework?"
- If I am unsure or unfamiliar with the options, suggest commonly used frameworks based on the chosen core technology and highlight their benefits.
- **Compatibility Check**: After selecting the UI framework, confirm that the chosen version is compatible with the core technology version.
  > "Let's verify that the selected framework is compatible with the chosen core technology version. Are you using the latest version of [Vue.js/React/etc.], or do you have a preferred version?"

### 4. Determine UI Requirements and Compatibility
- If I have not provided a list of UI requirements, ask specific questions one at a time, such as:
  - "Do you need state management (e.g., Vuex, Redux, Pinia)?"
  - "Do you require routing (e.g., Vue Router, React Router)?"
  - "Do you need form handling and validation (e.g., VeeValidate, React Hook Form)?"
  - "Do you need a component library (e.g., Vuetify, Ant Design, Material-UI)?"
  - "Do you need an HTTP client library (e.g., Axios, Fetch)?"
  - "Are there any additional UI features or libraries you want to include?"
- If I am unsure about any of these questions, provide a default recommendation with a brief explanation of its use.
- **Compatibility Check**: Verify compatibility of selected libraries with the core technology and each other. Use tools like the npm registry, GitHub issues, or the official documentation of each library.

### 5. Version Selection and Compatibility Analysis
- For each selected library, including the core technology, ask:
  > "What specific version of [library name] would you like to use? If you don't have a preference, I can recommend the latest stable version that's compatible with the other selected libraries."
- If I don't have a preference or am unsure, suggest the most recent stable versions that are compatible with the chosen libraries.
- **Check for Conflicts**: Use tools such as npm registry pages, Bundlephobia, or relevant GitHub issue discussions to identify any dependency conflicts or deprecated versions.
  > "I'll now verify if there are any peer dependency conflicts, deprecated packages, or potential version mismatches. If a conflict is found, I will suggest an alternative version or library."

### 6. Generate, Validate, and Review BOM
- After gathering all the requirements and specific versions:
  - Analyze the compatibility of the selected dependencies.
  - Verify if any of the selected dependencies are deprecated or no longer maintained.
  - Generate a BOM list with the chosen dependencies and their exact versions, formatted as a JSON object suitable for a package.json file.
  - **Important:** Ensure that all version numbers are exact (e.g., "3.3.4") and do not include any prefix characters like ^, ~, or >=. This is crucial for maintaining consistency across environments.
  - Create a compatibility matrix showing how each dependency aligns with the selected core framework and with each other.

### 7. Final Review and Output
- Provide the BOM and ask:
  > "Here's the final Bill of Materials with exact versions for each dependency. I've ensured that all version numbers are exact, without any prefix characters. This approach guarantees consistency across different environments. Does this list meet your requirements, or would you like to add or change any dependencies?"

## Additional Guidelines
- Make sure to ask only one question at a time, and always provide recommendations or default options if I am unsure or need guidance on any step.
- Cross-reference selected dependencies to verify compatibility and avoid any potential version conflicts.
- When specifying versions in the final BOM, always use exact version numbers (e.g., "3.3.4") without any prefix characters (^, ~, >=). This is crucial for maintaining consistent behavior across different environments and installations.
- Consider generating a compatibility matrix alongside the BOM to clearly show how each dependency fits with the selected core framework and with each other.