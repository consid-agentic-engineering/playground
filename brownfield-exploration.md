# ACME Order System — Workflow Examples

Use the ACME Order System to practice different Directed Agentic Engineering workflows.

## Workflow 1: Health Assessment

**Goal:** Understand the current state of the codebase — what's working, what's risky, what needs attention.

```bash
git clone https://github.com/consid-agentic-engineering/acme-order-system.git
cd acme-order-system
```

Run: `/health-assessment`

This will analyze:
- Code quality and architectural issues
- Security vulnerabilities (intentional: open CORS, hardcoded credentials, etc.)
- Technical debt and anti-patterns
- What needs refactoring

**Expected findings:**
- God classes (OrderService, CustomerService doing too much)
- Mixed architectural patterns (services + direct repo access in controllers)
- Hardcoded values scattered throughout
- Duplicate business logic (discount calculation in 3 places)
- Missing error handling and validation

## Workflow 2: Brownfield Exploration

**Goal:** Map the codebase structure, understand data flow, identify patterns and problems.

Run: `/brownfield-explore`

This will help you:
- Trace how orders flow through the system (controller → service → repository)
- Identify inconsistencies in naming and patterns
- Find duplicated logic
- Understand the layered architecture

**Key observations:**
- Controllers sometimes bypass services (mixed patterns)
- Services handle pricing, email, inventory — too many concerns
- Two different discount calculation approaches
- Inconsistent naming: `getOrder` vs `retrieveOrder` vs `fetchCustomer`

## Workflow 3: Planning a Refactor

**Goal:** Design improvements to the architecture.

After running health assessment and brownfield exploration:

1. **Pick a problem area:**
   - Extract pricing logic into a dedicated service
   - Consolidate discount calculations
   - Fix inconsistent naming conventions
   - Add proper error handling

2. **Create an OpenSpec change:**
   - Use `/openspec-new-change` to structure your refactoring
   - Define what you're changing and why
   - Plan the implementation in artifacts

3. **Implement with `/openspec-apply-change`**

## Workflow 4: Learning Path

**For teams new to Directed Agentic Engineering:**

1. **Session 1 — Understanding:**
   - Clone the repo
   - Run `/health-assessment` to see the current state
   - Read the code and git history to understand how it evolved
   - Discuss: "What would you change first and why?"

2. **Session 2 — Planning:**
   - Run `/brownfield-explore` to map the codebase
   - Use `/architect` or `/target-architecture` to design improvements
   - Create an OpenSpec change with the improvements

3. **Session 3 — Delivery:**
   - Implement the change using `/openspec-apply-change`
   - Review with `/openspec-verify-change`
   - Close the change with `/openspec-archive-change`

## What makes ACME a good practice example

- **Realistic:** Real code with real decisions (good and bad)
- **Complete:** Full git history shows how it evolved
- **Intentional anti-patterns:** Security issues and architectural problems are deliberate, not accidental
- **Self-contained:** Spring Boot + AngularJS, runs locally, H2 database
- **Safe to experiment:** Read-only repository, your changes stay local

## Getting started

```bash
# Clone your own copy
git clone https://github.com/consid-agentic-engineering/acme-order-system.git
cd acme-order-system

# Build and run
mvn clean package
java -jar target/order-management-1.0.0.jar

# Explore the git history
git log --oneline  # See all 11 commits
git show <commit>  # Examine individual commits

# Start a health assessment
/health-assessment
```

Then pick a workflow above and practice with it.
