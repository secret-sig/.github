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

* **Secret**: A piece of sensitive information that, if exposed, could pose a
  risk to an individual or organization. The sensitivity of a secret is highly
  contextual.
  * Example of a high-impact secret: A private key for signing software
    releases.
  * Example of a contextual secret: An email address may be a secret in the
    context of a private employee list but public on a personal blog.
* **Leak**: The unauthorized or unintentional exposure of data. Not all exposed
  data constitutes a high-risk leak.
  * Example of a leak: A database of user credentials posted on a public forum.
  * Example of non-leak data: A publicly shared, unused SSH key pair created
    for a tutorial is technically exposed data, but not a meaningful leak as it
    protects no sensitive system.
* **Finding**: A potential secret identified by a scanner. A finding is not a
  confirmed leak until it has been validated.
* **Verification**: The process of confirming that a finding meets the
  requirements of a secret through static analysis.
  * Example: A scanner flags a 40 character string in a file named
    `config.yaml`. Verification confirms this string matches the precise format
    of a GitHub personal access token.
  * Example: A string is confirmed to match the `ddd-dd-dddd` format and is found
    near the keyword `ssn` in a log file.
* **Validation**: The process of determining if a verified finding is currently
  active through dynamic analysis.
  * Example: Following verification of a GitHub token, validation involves
    querying the GitHub API with that token to see if it authenticates
    successfully and what permissions it holds. A successful query validates
    the finding as a live leak.
  * Example: The verified SSN is queried against the production customer
    database, confirming it belongs to a real customer.
