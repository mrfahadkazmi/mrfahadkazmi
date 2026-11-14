# Software quality and evidence — how I evaluate projects

I document my projects using evidence that a reviewer can distinguish from design intent.

## Working functionality

Record a short, genuine end-to-end demo: input, action, visible progress, output and error handling. Hide account names, private URLs, cookies and credentials. Do not use simulated progress or an edited success screen as proof.

## Test evidence

For each important behavior write: test name, expected result, actual result, environment, date, and outcome (**PASS**, **FAIL**, **INCOMPLETE**, or **NOT RUN**). Automated tests that use mocks are explicitly labeled. A screenshot or source-code inspection is not a substitute for an end-to-end test.

## Code quality

Review module boundaries, readability, error handling, dependency management, safe secret handling and automated testing. Source code must be reviewed before claiming that quality checks pass. Unavailable source should be marked as such.

## Security and publishing

Do not publish API keys, Kaggle credentials, cloud tokens, SSH private keys, browser cookies, personal documents or raw configuration files containing secrets. Avoid uploading all project sources blindly; check third-party license obligations and remove sensitive values first.

## Honest limitations

A portfolio case study can describe an implementation even when a particular runtime behavior has not been verified. Clear limitations make future testing goals visible and avoid overstating expertise.

[Projects and evidence](../projects/README.md)
