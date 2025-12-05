# Security Policy for WatchWise-AI-Content-Recommendation-Web-App

This policy outlines the security practices for the `WatchWise-AI-Content-Recommendation-Web-App` repository, maintained by `chirag127`. We adhere to the **Apex Technical Authority's** philosophy: "Zero-Defect, High-Velocity, Future-Proof."

## 1. Reporting a Vulnerability

We take security very seriously. If you discover a security vulnerability within this project, please follow these steps immediately:

1.  **Do Not** create a public issue, pull request, or post on public forums.
2.  Private disclosure is mandatory for all security concerns.

### Private Reporting Channels

To report a vulnerability privately to the maintainer (`chirag127`), please use one of the following methods:

*   **Email:** Send a detailed report to `security+watchwise@chirag127.dev` (This is a placeholder; replace with an actual security contact if available).
*   **GitHub Security Advisory:** Utilize the built-in GitHub Security Advisories feature associated with this repository to create a private report.

## 2. Vulnerability Disclosure Timeline

Upon receiving a vulnerability report, the Apex team commits to the following timeline:

| Stage | Target Response Time |
| :--- | :--- |
| Initial Acknowledgment | Within 48 hours |
| Diagnosis & Triage | Within 5 business days |
| Patch Development | Dependent on Severity (See below) |
| Public Disclosure | After patch release, coordinated with the reporter. |

## 3. Severity Levels and Patch Expectations

Patch urgency is determined by the security impact:

*   **Critical (RCE, Data Leakage):** Immediate patching cycle. All other feature development halts until a fix is deployed and verified via CI/CD.
*   **High (Authentication Bypass, Privilege Escalation):** High priority patch within 7 days.
*   **Medium (Information Disclosure, Minor XSS vectors):** Addressed in the next scheduled minor release cycle (typically 14-30 days).
*   **Low (Best Practice Violations, Minor Configuration Issues):** Addressed during routine refactoring or maintenance.

## 4. Development & Defense Standards (2026 Compliance)

This project employs proactive security measures aligned with the Apex Technical Authority directives:

*   **TypeScript Strictness:** All TypeScript code enforces `strict: true` to catch potential type coercion vulnerabilities.
*   **Dependency Scanning:** Automated scanning using GitHub Dependabot and/or Snyk integration (configured in `ci.yml`) runs on every push and pull request.
*   **Vite/Tailwind Hardening:** Ensuring that client-side code built via Vite does not expose sensitive configurations, and CSS sanitization is maintained.
*   **AI Component Security:** Since this involves an AI recommendation engine, all external API calls (e.g., to LLMs) are routed through secure, validated adapters, ensuring strict input sanitization to prevent prompt injection attacks on the service layer.

## 5. Scan & Verification

All security patches require successful validation through:

1.  **CI Workflow (`.github/workflows/ci.yml`):** Must pass all unit tests (Vitest) and integration checks.
2.  **E2E Testing (Playwright):** Must pass dedicated security regression test suites before merging to `main`.

For further architectural and process alignment, please refer to our primary source of truth:

*   [Contributing Guidelines](./CONTRIBUTING.md)
*   [Agent Directives](./AGENTS.md)

--- 

*Last Reviewed: December 2025*