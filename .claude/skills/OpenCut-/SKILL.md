```markdown
# OpenCut- Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill guides you through the development conventions and workflows of the OpenCut- repository, a Rust codebase with a focus on clear structure and maintainability. You'll learn how to follow its coding standards, commit message patterns, and testing practices to contribute effectively.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `myModule.rs`, `dataParser.rs`

### Import Style
- Use **relative imports** within modules.
  - Example:
    ```rust
    mod utils;
    use crate::utils::helperFunction;
    ```

### Export Style
- Use **named exports** for functions and types.
  - Example:
    ```rust
    pub fn processData(input: &str) -> Result<()> {
        // implementation
    }
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use the `feat` prefix for new features.
  - Example:
    ```
    feat: add support for custom data parsers
    ```
- Keep commit messages concise (average 47 characters).

## Workflows

### Feature Development
**Trigger:** When adding a new feature or module  
**Command:** `/feature-dev`

1. Create a new file using camelCase naming.
2. Implement the feature using relative imports for dependencies.
3. Export public functions/types using named exports.
4. Write or update corresponding test files (`*.test.*`).
5. Commit changes using the `feat` prefix and a concise message.
6. Push your branch and open a pull request.

### Code Testing
**Trigger:** When verifying code correctness  
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Run tests using the Rust test runner or your preferred method.
3. Review test output and fix any failures.
4. Repeat until all tests pass.

## Testing Patterns

- Test files follow the pattern: `*.test.*` (e.g., `parser.test.rs`).
- The testing framework is not specified; use standard Rust testing tools unless otherwise noted.
- Example test:
  ```rust
  #[cfg(test)]
  mod tests {
      use super::*;

      #[test]
      fn test_process_data() {
          assert!(processData("input").is_ok());
      }
  }
  ```

## Commands
| Command         | Purpose                                   |
|-----------------|-------------------------------------------|
| /feature-dev    | Start a new feature development workflow   |
| /run-tests      | Run all tests in the codebase             |
```