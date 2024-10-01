# Software design

### Development Stack and Libraries

Selecting a secure development stack involves careful consideration of programming languages, frameworks, and tools with a strong track record in security. It's essential to keep libraries and dependencies up to date to address potential security vulnerabilities.

&#x20;Especially when the functionality is needed for secure operation the implementation should use well-tested and maintained components and libraries in favor of implementing functionalities from scratch. This applies specifically to:

&#x20;·         JWT parsing & handling

·         Certificate parsing & handling

·         Input validation

·         Authentication

·         Authorization

·         Database interactions (e.g. an ORM framework)

·         Output escaping in user interfaces (e.g. templating frameworks)

·         Cryptography, including password storage

&#x20;The development stack should be chosen accordingly.

&#x20;**Secure Code Design**

Secure code design encompasses foundational principles, including rigorous input validation, output encoding, and error handling. Implementing security design patterns, such as the Principle of Least Privilege or Fail-Safe Defaults, is crucial for minimizing potential vulnerabilities. Practical code examples demonstrate how to apply these principles effectively.

&#x20;·         Version Control: Use version control to manage code changes.

·         Validate Inputs: Always validate API inputs, operator inputs, and data from peer services. Use standardized mechanisms like OpenAPI specifications for validation.

·         Certificate and JWT Validation: Validate certificates and JWTs for format, validity period, and other parameters using standard components.

·         Secret Management: Keep operational secrets secure and separate from source code repositories.

·         Access Restrictions: Limit access to production machines, automate software deployment, and log all access and deployments. Restrict the number of users with production access.

·         Code Review: Ensure all code changes are reviewed by a second developer before merging.

·         Enforce access control service-wide: API and operator endpoints must have access control applied. This should be designed into the service architecture and “fail closed” so that endpoints must have explicit access restrictions – access control must not rely on ad-hoc checks per action/endpoint that may be omitted or have logic errors.

&#x20;**Strict checks that “fail closed”**

When validating requests and comparing registrations, the implementation should be strict; incomplete data (including failure to request required information from third parties) is not acceptable and should prevent requests from completing.

&#x20;The goal is to prevent leaking sensitive information and erroneous positive statements about parties (I.e., “Party X is an active member of an association”) due to misconfiguration, bugs, and deliberate attacks.

&#x20;The core principle is that access is denied except for complete and valid requests.

&#x20;The above principle must also be applied to the service’s implementation; any path + request method combination not explicitly allowed with specified access controls must be denied.

&#x20;In addition to the above section on strict checks that “fail closed”, centralize the access control mechanisms so no endpoints can be accidentally exposed without correct controls.

&#x20; **Centralize input validation**

Input validation on endpoints must be centralized so no endpoints can be accidentally exposed without correct input validation. Apply the “fail closed” principle.

&#x20;**Automated tests & CI/CD**

The development process must use automated tests to check regressions and validate new functionality. The automated deployment mechanism should ensure that new releases pass all automated tests before deployment. Releases must be tracked in the audit log.

&#x20;Besides unit tests and regressions tests the CI/CD pipeline can also be employed to perform:

·                    Dependency scanning

·                    Static Application Security Testing (SAST)

·                    Dynamic Application Security Testing (DAST)

