# Step 1: Initialize a new npm project
```bash
npm init -y

# Step 2: Install Cypress and TypeScript as dev dependencies
npm install --save-dev cypress typescript

# Step 3: Install TypeScript definitions for Cypress
npm install --save-dev @types/cypress

# Step 4: Create a tsconfig.json file for TypeScript configuration
echo '{
  "compilerOptions": {
    "target": "es5",
    "lib": ["es5", "dom"],
    "types": ["cypress"]
  },
  "include": ["**/*.ts"]
}' > tsconfig.json

# Step 5: Create a cypress folder with a integration subfolder for tests
mkdir -p cypress/e2e

# Step 6: Create a simple test file in the integration folder
echo 'describe('template spec', () => {
  it('passes', () => {
    cy.visit('https://example.cypress.io')
  })
})' > cypress/e2e/spec.cy.ts

# Step 7: Add a script to package.json to run Cypress
# This step needs to be done manually. Add the following line to the "scripts" section of your package.json:
# "cypress:open": "cypress open"