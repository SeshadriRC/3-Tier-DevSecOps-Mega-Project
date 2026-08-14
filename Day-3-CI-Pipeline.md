**Infra Setup**

<img width="669" height="410" alt="image" src="https://github.com/user-attachments/assets/b38fb938-78c4-4089-85de-30a1dcbf38a5" />



**CI structure**
<img width="1274" height="689" alt="image" src="https://github.com/user-attachments/assets/3573c196-63e6-420e-8fe5-5976e6e6fda0" />

```bash
Developer Commit
       │
       ▼
Git Checkout
       │
       ▼
Compilation
(Syntax & Semantic Checks)
       │
       ▼
GitLeaks Scan
(Check for passwords, tokens,
API keys, secrets)
       │
       ▼
Trivy Filesystem Scan
(Check dependency vulnerabilities
from pom.xml, package.json,
requirements.txt, .csproj, etc.)
       │
       ▼
Unit Testing
(Execute test cases)
       │
       ▼
SonarQube Analysis
(Bugs, Vulnerabilities,
Code Smells, Coverage)
       │
       ▼
Quality Gate Check
(0 Bugs, 0 Vulnerabilities,
Coverage >= 80%)
       │
       ▼
Docker Image Build
       │
       ▼
Trivy Image Scan
(Check OS packages &
application libraries
inside Docker image)
       │
       ▼
Push Image to Docker Hub
```

---

Interview Explanation of Each Stage

1. Git Checkout

- Pulls the latest source code from GitHub/GitLab/Bitbucket.
- Makes the code available on the Jenkins agent for execution.

---
2. Compilation

- Converts source code into executable/build artifacts.
- Detects syntax and semantic errors early.

Example:
mvn compile

---

3. GitLeaks Scan

Detects hardcoded secrets in source code.

Examples:
Passwords
API Keys
AWS Access Keys
Tokens

---
4. Trivy Filesystem Scan

Scans project dependencies before building.

Reads files such as:
pom.xml
package.json
requirements.txt
.csproj

- Compares dependency versions against CVE databases.

---
5. Unit Testing

- Executes developer-written test cases.
- Ensures code behaves as expected.

Example:
mvn test

---
6. SonarQube Analysis

Checks:

Bugs → Coding logic issues
Vulnerabilities → Security risks
Code Smells → Maintainability issues
Code Coverage → % of code covered by tests
Duplications → Repeated code

---
7. Quality Gate Check

Compares SonarQube results with organizational standards.

Example:

- Metric	Actual	RequiredBugs	5	0
- Vulnerabilities	1	0
- Coverage	75%	≥ 80%

<img width="1115" height="314" alt="image" src="https://github.com/user-attachments/assets/aa04dd38-768e-4180-978d-25865802aae4" />


Result:

❌ Pipeline Fails

If:
<img width="1104" height="364" alt="image" src="https://github.com/user-attachments/assets/42b67136-8f39-46fd-94be-332bb0e71fa0" />


Result:

✅ Pipeline Continues

---
8. Docker Image Build

Creates a Docker image from the application source code.

Example:

docker build -t myapp:1.0 .

---
9. Trivy Image Scan

Scans the built Docker image.

Checks:

OS package vulnerabilities
Application dependency vulnerabilities
Critical/High CVEs

Example:

trivy image myapp:1.0

---
10. Push Image to Docker Hub

Pushes the scanned and approved image to the registry.

Example:

docker push myrepo/myapp:1.0

Short Interview Answer

The pipeline starts with Git checkout, compilation, GitLeaks secret scanning, Trivy filesystem dependency scanning, unit testing, SonarQube analysis, and quality gate validation. Once the code passes all quality and security checks, the Docker image is built, scanned using Trivy, and then pushed to Docker Hub.
