# codepath-ai301-contribution
# Contribution #205:  Add compatibility test for $bitXor 

**Contribution Number:** #205

**Student:** Huyen Huynh

**Issue:** [GitHub issue link]  (https://github.com/documentdb/functional-tests/issues/205)

**Status:** [Phase I / Phase II / Phase III / Phase IV] 
[x] Phase I is completed
[x] Phase II is completed
[ ] Phase III is completed
[ ] Phase IV is completed
---

## Why I Chose This Issue

 I chose #205: Add compatibility test for $ bitXor because it aligns with my Python experience and my goal to improve test-writing skills. The issue is labeled "good first issue" and has clear contribution instruction. 

 I'm interesed in this because:
 1. I have extensive experience using Python in both personal and academic projects, which will help me understand and implement the required tests.
 2. I understand how bitwise XOR works
 3. I want to gain more experience writing and maintaining tests.

From reading the issue thread, I understand that compatibility testing for $bitXor is currently missing. My contribution will be add the necessary test coverage and help resolve the issue.

I have left Left a comment on the issue introducing myself but I haven't received a response back yet.


---

## Understanding the Issue

### Problem Description

DocumentDB is a MongoDB compatible open source document database built on PostgreSQL. It provides a built-in implementation of a document-oriented NoSQL database, allowing seamless CRUD operations on BSON data types withing a PostgreSQL. It also supports a variety of advanced operations, including full-text searches, geospatial queries, and vector search.

DocumentDB is currently missing the functional testings for $bitXor. BitXor is a bitwise XOR (exlusive or) of two numbers that returns a bit of "1" if two bits are different, and a bit of "0" otherwise. Hence, the expected results should follow the standard behavior of the XOR operation.

### Expected Behavior

The tests will cover xor math (including single-operand and empty-list cases), null and missing values, accepted data types (int and long) with correct int/long result type, and rejection of non-integer types (decimals, fractional doubles, strings, booleans, etc.)


### Current Behavior

As of now, there is only one basic test for bitwise XOR, which is checking two integers. 

### Affected Components

New testing files for bitwise XOR functionality will be added to the project at **documentdb_tests/compatibility/tests/core/operator/expressions/bitwise/bitXor**. No other modifications are expected to happen.

---

## Reproduction Process

### Environment Setup

I have no trouble with environment setup as the project provided a clear instrucion.

Working Branch: https://github.com/htthuyen/functional-tests/tree/feature/add-compatibility-test-for-XOR 

### Steps to Reproduce

1. Read the provided contributing.md 
2. Install requirements.txt to install required packages and dependencies
3. Research the given testing documents, including project structure, test coverage, and test format
4. Sucessfully run the given sample test

### Reproduction Evidence

- **Commit showing reproduction:** [Link to commit in your fork]
- **Screenshots/logs:**
  - Project overview:
    
  <img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4b7b6edf-0c5f-4912-b73e-18d9e0be1760" />

  
  - Run sample test:

    <img width="1527" height="273" alt="image" src="https://github.com/user-attachments/assets/97ac0834-8f74-4385-a6f5-28d567c90cf6" />

---

## Solution Approach

### Proposed Solution

  I will add test case files under documentdb_tests/compatibility/tests/core/operator/expressions/bitwise/bitXor, expanding coverage of the $bitXor aggregation expression beyond the existing smoke test. They
  include XOR math (including single-operand and empty-list cases), null and missing values, accepted data types (int and long) with correct int/long result-type promotion, and rejection of non-integer types
  (decimals, fractional doubles, strings, booleans, etc.).

### Implementation Plan

  **Understand:** The project has only a smoke test for $bitXor; the edge-case behaviors of the bitwise XOR expression are not yet covered.

  **Match:** The repo's fully built-out bitwise query suite (e.g. core/operator/query/bitwise/bitsAllSet) shows the standard property-file split; I will follow that structure and the data-driven TestCase/pytest_params
  idioms for my tests.

  **Plan:**
  1. Add the missing cases listed in the Proposed Solution, with each property (math, null/missing, accepted types, type rejection) in its own test file.
  2. Run the suite against MongoDB as the oracle to confirm expected values, then against DocumentDB to record its behavior; verify no regressions. 

  **Review:** Will self-review against the project's CONTRIBUTING.md and commit-message conventions before opening a PR.

  **Evaluate:** The new tests should pass against the MongoDB oracle and classify DocumentDB's support for each $bitXor property (PASS / FAIL / UNSUPPORTED). All existing tests should continue to pass.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
