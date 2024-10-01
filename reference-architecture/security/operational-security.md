# Operational security

Operational security is critical to ongoing protection. Access controls and permissions are vital for restricting employee access to sensitive resources. Regular access reviews and audit trails ensure accountability and security maintenance.&#x20;

### No manual editing possible in Association Register

An Association Register is a core part of automated trust assessment. This requires both:

* Rigorous design and testing for IT-security weaknesses (cryptographic libraries, protocols, pentesting, supply chain attacks etc.)
* An operational security process that minimizes the risk of humans as attack vector (social engineering, pressure) to compromise the integrity of the register&#x20;

The human attack vector is considered to be the most risky: onboarding should therefore be a one-way automated process in three separate steps (see also onboarding T\&Cs Association articles):

* Collecting information (automated and/or manual)
* Verifying information and test trust chain (automated)
* Committing to the register (manual action by functionary)&#x20;

Modification of information should only be possible by deleting or deprecating information, followed by a new onboarding process.

### Roles and access

Define roles for actors and restrict access to relevant actions or endpoints based on these roles. This ensures that users only have access to the functionalities necessary for their roles, reducing the risk of unauthorized access.&#x20;

### Security Testing

Security testing involves systematic (and automatic) assessments to uncover vulnerabilities. This includes penetration testing, vulnerability scanning, and code reviews. Integrating security testing into the development lifecycle is critical for identifying and rectifying security weaknesses.&#x20;

### Keep components up-to-date

For this process it is helpful to have an inventory of all software (and software dependencies), sometimes referred to as a software Bill of Materials. This could be integrated in the CI/CD pipeline.

During development and operations should have processes in place to keep the system’s dependencies up to date and to make sure dependencies are still supported by the vendor. CVEs should be monitored for issues and workarounds.

The development cycle should make it possible to release bugfixes and security-fixes on a fast schedule.&#x20;

### Backups

Backups to recover from crashes and/or data loss must be in place. Access to backups must be restricted to the CISO.

&#x20;
