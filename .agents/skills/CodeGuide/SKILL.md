```markdown
# CodeGuide Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides a comprehensive guide to contributing to the CodeGuide repository, a JavaScript codebase focused on documentation without a detected framework. It covers coding conventions, file organization, and step-by-step workflows for adding new documentation sections. The guide also outlines testing patterns and helpful commands to streamline contributions.

## Coding Conventions

**File Naming**
- Use **kebab-case** for all file names.
  - Example: `add-section.js`, `user-guide.md`

**Import Style**
- Use **relative imports** for all modules.
  ```js
  import { getConfig } from './config.js';
  ```

**Export Style**
- Use **named exports**.
  ```js
  // In utils.js
  export function formatTitle(title) { ... }
  export const DEFAULT_SECTION = 'Introduction';

  // Importing
  import { formatTitle, DEFAULT_SECTION } from './utils.js';
  ```

## Workflows

### Add New Documentation Section
**Trigger:** When you want to add a new section or article to the documentation.
**Command:** `/new-doc-section`

1. **Update Navigation/Sidebar**
   - Edit `docs/.vuepress/config.js` to register the new section or article in the navigation or sidebar.
   - Example:
     ```js
     // docs/.vuepress/config.js
     module.exports = {
       themeConfig: {
         sidebar: [
           '/md/introduction.md',
           '/md/new-section.md', // <-- Add your new file here
         ]
       }
     };
     ```

2. **Add Markdown Content**
   - Create or update a markdown file in `docs/md/` or `docs/md/project/` with your new content.
   - Example:
     ```
     docs/md/new-section.md
     ```
     ```markdown
     # New Section

     Welcome to the new section of the documentation!
     ```

3. **Add Related Images**
   - Place any images needed for the article in `docs/.vuepress/public/images/article/` within an appropriate subfolder.
   - Example:
     ```
     docs/.vuepress/public/images/article/new-section/diagram.png
     ```
   - Reference images in markdown:
     ```markdown
     ![Diagram](../../.vuepress/public/images/article/new-section/diagram.png)
     ```

## Testing Patterns

- **Test File Pattern:** All test files follow the `*.test.*` naming convention.
  - Example: `utils.test.js`
- **Testing Framework:** Not explicitly detected. Check existing test files for patterns or consult project maintainers for preferred frameworks.

## Commands

| Command           | Purpose                                                      |
|-------------------|--------------------------------------------------------------|
| /new-doc-section  | Start the workflow to add a new documentation section/article |

```