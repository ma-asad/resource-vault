### Git Conventional Commits Cheatsheet

#### Conventional commit message structure

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

The conventional commit message structure consists of 4 main parts:

1. **Type**: A conventional type that specifies the kind of change made in the commit.
2. **Scope** (optional): A scope that specifies the part of the codebase that was affected by the change.
3. **Description**: A short, imperative tense description of the changes made in the commit.
4. **Optional** (optional): Optional body and footer(s) to provide more details or metadata about the commit.

#### Types

The types indicate the nature of the changes made in the commit.

##### `feat`: A new feature

```
feat(user-profile): add ability to upload profile picture
feat: add support for dark mode
```

Use `feat` when introducing a new feature or functionality to the codebase.

##### `fix`: A bug fix

```
fix(auth): correct password validation logic
fix: resolve issue with file uploads on Safari
```

Use `fix` when fixing a bug or resolving an issue in the codebase.

##### `docs`: Documentation changes

```
docs(readme): update installation instructions
docs: add contribution guidelines
```

Use `docs` when updating or adding documentation files (e.g., README, CONTRIBUTING, etc.).

##### `style`: Changes that do not affect the meaning of the code (formatting, missing semi-colons, etc.)

```
style(components): format code according to style guide
style: fix indentation in server.js
```

Use `style` when making changes that affect the code formatting or styling but do not change the functionality.

##### `refactor`: A code change that neither fixes a bug nor adds a feature

```
refactor(auth): extract authentication logic to separate module
refactor: migrate to React functional components
```

Use `refactor` when restructuring or reorganizing existing code without changing its functionality.

##### `test`: Adding or modifying tests

```
test(user): add unit tests for UserService
test: improve test coverage for utils
```

Use `test` when adding or modifying test files or improving test coverage.

##### `chore`: Changes to build processes or auxiliary tools and libraries

```
chore(deps): update dependency mongoose to v5.9.7
chore: add prettier configuration
```

Use `chore` when making changes to build processes, auxiliary tools, or updating dependencies.

#### Scopes (Optional)

Scopes refer to the part of the codebase that was affected by the change. They help provide more context about the changes made in the commit. Scopes should be placed within parentheses after the type.

```
feat(user-profile): add ability to upload profile picture
fix(auth): correct password validation logic
refactor(auth): extract authentication logic to separate module
```

In the examples above, `user-profile` and `auth` are the scopes indicating the specific parts of the codebase that were modified.

Scopes can be:

- A specific module or component name (e.g., `user-profile`, `auth`, `header`, etc.)
- A directory or file name (e.g., `server`, `utils`, `styles`, etc.)
- A broader category or feature area (e.g., `api`, `ui`, `database`, etc.)

If the changes affect multiple parts of the codebase or the entire project, omit the scope.

#### Descriptions

Write descriptions in the imperative present tense and provide a concise summary of the changes made in the commit. They should be clear and descriptive, allowing others to understand the purpose of the commit at a glance.

```
feat(user-profile): add ability to upload profile picture
fix(auth): correct password validation logic
docs(readme): update installation instructions
```

#### Bodies (Optional)

Use bodies to provide additional details or context about the changes made in the commit. Separate them from the subject line by a blank line. Bodies can include bullet points or paragraphs to explain the changes more thoroughly.

```
feat(user-profile): add ability to upload profile picture

- Add new upload component
- Add backend route for handling file uploads
- Update user model to store profile picture URL
```

Bodies are especially useful when the changes are complex or involve multiple aspects of the codebase. They can help provide a more comprehensive understanding of the commit.

#### Footers (Optional)

Footers can include keywords like `Fixes`, `Closes`, `Resolves`, followed by the issue or pull request number. This helps maintain traceability and can automatically close issues or pull requests when the commit is merged.

#### Footers (Optional)

Use footers to reference issues, pull requests, or other metadata related to the commit. Separate them from the body by a blank line.

##### Referencing Issues

```
fix(auth): correct password validation logic

Fixes #42
```

```
feat(user-profile): add ability to upload profile picture

Closes #123
Resolves #456
```

##### Breaking Changes

If the commit introduces a breaking change (a change that breaks backward compatibility), either:

1. Include a `BREAKING CHANGE` footer with a description of the breaking change.

```
feat(database): migrate to MongoDB

BREAKING CHANGE: The application now requires MongoDB to be installed and running. Previous data stored in the SQL database will not be migrated automatically.
```

2. Or, append a `!` after the `type/scope` in the commit message.

```
refactor(auth)!: rename 'getUserToken' to 'getAuthToken'

BREAKING CHANGE: The 'getUserToken' function has been renamed to 'getAuthToken'. All usages of 'getUserToken' need to be updated.
```

Using the `!` is a more concise way of indicating a breaking change, while the `BREAKING CHANGE` footer allows providing a more detailed description of the breaking change, including any necessary migration steps or instructions for updating existing code.

Reference:
[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)