# **Secret Scanning SIG (SSSIG)**

## **Mission**

To enable open source and vendor tools to move beyond basic scanning to solve
novel problems in secret leak detection, remediation, and prevention.

## **Vision**

An ecosystem of tools and services built around open collaboration that
proactively protects data, freeing individuals and organizations to innovate.

## **Guiding Principles**

* **Collaboration**: We prioritize working together to solve common problems.
  We aim to integrate with and enhance existing tools and services, not replace
  them.
* **Do No Harm**: We operate with respect and empathy. The goal is to partner
  with organizations to solve problems, not to assign blame or publicly shame
  them for leaks. All activities should be conducted with the aim of protecting
  organizations and their users.
* **Action-Oriented**: We focus on producing practical, actionable outcomes,
  whether that's code, documentation, or standards.

## **Scope**

### **In-Scope**

* **Advanced Detection Techniques**: Developing novel methods for identifying
  secrets that go beyond simple pattern matching, including contextual analysis
  and validation.
* **Knowledge Sharing**: Acting as a central hub for sharing best practices,
  case studies, and research.
* **Shared Terminology**: Developing a common vocabulary to map concepts across
  different tools, frameworks, and teams.
* **Tool Integration**: Promoting flexible ways for tools to work together,
  such as through shared data formats and APIs without enforcing rigid
  standards.
* **Reference Implementations**: Providing permissively licensed, reference
  implementations of specific parts of the scanning process for tools and
  vendors to use.
* **Benchmarks**: Establishing neutral benchmarks for evaluating the
  effectiveness of different scanning tools and techniques.

### **Out-of-Scope**

* **Replicating Commercial Offerings**: This SIG will not build tools or
  services that directly compete with established commercial secret scanning
  solutions. The focus is on innovation and collaboration, not market
  competition.
* **Disclosure of Active Leaks**: The SIG will not be a platform for disclosing
  specific, unmitigated leaks. It is a forum for discussing tools and
  techniques, not a vulnerability disclosure platform.
* **Product Endorsements**: The SIG will remain vendor-neutral and will not
  endorse specific commercial products.

## **Definitions**

* **Secret**: Any piece of sensitive information that, if exposed, could pose a
  risk to an individual or organization. The sensitivity of a secret is highly
  contextual.
  * Example:
    * High Impact: Private signing key for software releases
    * Contextual: Email address (e.g. in private employee list vs on a personal
      blog)
* **Leak**: The unauthorized or unintentional exposure of a secret. Exposing
  non-sensitive data is not a leak.
  * Examples:
    * Leak: A database of user credentials posted on a public forum.
    * Leak: SSH private key pushed to a public git repo
    * Leak: Customer data posted into another customer's support ticket
    * Not a Leak: A publicly shared, _unused_ SSH key pair created _only_ for a
      tutorial
* **Finding**: A _potential_ secret identified by a scanner. A finding is not a
  confirmed secret until it has been validated.
* **Verification**: The process of confirming that something meets the
  requirements for a finding. Verification is part of the process of producing
  a finding.
  * Examples:
    * Length/format checks
    * Entropy checks
    * Filtering known false positives
    * Keyword checks
    * Contextual analysis
* **Validation**: The process of confirming that a finding is a true positive.
  It may not be possible to automate validation in every case.
  * Examples:
    * Successfully authenticating with a credential finding
    * Confirming an SSN finding matches an SSN in the customer database
    * Contacting the repository owner and asking
