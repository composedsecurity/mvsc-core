# MVSC-Core v0.1

**Minimum Viable Secure Code**

A practical, language-agnostic baseline of security controls for developers and AI agents building secure software.

## What is MVSC-Core?

MVSC-Core is the foundational checklist that defines "secure enough to ship" for any application. Think of it as the equivalent of [MVSP](https://mvsp.dev/) (Minimum Viable Secure Product) but focused on code-level security rather than organizational controls.

Whether you're a human reviewing code or configuring an AI agent, these are the non-negotiables that catch the most critical vulnerabilities before they make it to production.

## Why MVSC-Core?

- **For Developers**: A quick sniff test before you commit
- **For Code Reviewers**: The baseline checklist that must pass
- **For AI Agents**: Add these rules to your prompt, skill, or `agents.md` file to nudge your favorite dev agent into producing code that passes the security sniff test
- **For Teams**: A shared language for "what does secure code look like?"

This isn't about perfection—it's about catching the vulnerabilities that matter most, fast.

## The MVSC-Core Checklist

### **MVSC-CORE-01** — Define trust boundaries.
Know what's user input, what's trusted, and where data crosses from untrusted to trusted zones.

### **MVSC-CORE-02** — Validate all inputs.
Never trust user input. Validate type, length, format, and range. Reject bad data early.

### **MVSC-CORE-03** — Encode all outputs.
Prevent injection attacks by encoding data for the context it's used in (HTML, SQL, shell, etc.).

### **MVSC-CORE-04** — Use parameterized queries.
Never concatenate user input into SQL. Use prepared statements or ORMs with parameterization.

### **MVSC-CORE-05** — Authenticate first, authorize second.
Verify who the user is, then check if they're allowed to do what they're asking.

### **MVSC-CORE-06** — Fail securely.
When something breaks, fail closed. Don't leak sensitive info in error messages.

### **MVSC-CORE-07** — Log security events.
Log authentication attempts, authorization failures, and suspicious activity. Don't log secrets.

### **MVSC-CORE-08** — Encrypt sensitive data.
Use TLS for data in transit. Encrypt secrets at rest. Never commit keys to repos.

### **MVSC-CORE-09** — Use secure defaults.
Default to deny, HTTPS-only, secure cookies, and minimal permissions.

### **MVSC-CORE-10** — Avoid hardcoded secrets.
Use environment variables, secret managers, or vaults. Never hardcode credentials.

### **MVSC-CORE-11** — Keep dependencies updated.
Use tools to scan for known vulnerabilities in third-party libraries and update regularly.

### **MVSC-CORE-12** — Implement rate limiting.
Protect against brute force and DoS by rate limiting sensitive endpoints.

### **MVSC-CORE-13** — Use CSRF protection.
Protect state-changing operations with anti-CSRF tokens.

### **MVSC-CORE-14** — Sanitize file uploads.
Validate file types, scan for malware, and store uploads outside the webroot.

## How to Use MVSC-Core

### For Human Developers
Run through this checklist before committing code. If you can't check a box, document why and create a ticket to fix it.

### For AI Coding Agents
Add MVSC-Core to your agent's context:
```
# Security Requirements
Follow MVSC-Core v0.1: https://github.com/composedsecurity/mvsc-core

Prioritize:
- Input validation
- Output encoding
- Parameterized queries
- Secure defaults
- No hardcoded secrets
```

### For Teams
Make this part of your definition of done. Code doesn't ship unless it passes MVSC-Core.

## What's Next?

MVSC-Core is the baseline. We're building domain-specific versions:
- **MVSC-Web**: Web application security controls
- **MVSC-Mobile**: Mobile app security
- **MVSC-IoT**: IoT and embedded security
- **MVSC-Robots**: Robotics security (yes, really)

## Contributing

Found a critical control we missed? Open an issue or PR. MVSC-Core should stay short and focused on the vulnerabilities that matter most.

## License

Apache 2.0 — Use it, share it, make software more secure.

## Learn More

Read the launch post: [MVSC-Core: Minimum Viable Secure Code](https://composedsecurity.medium.com/mvsc-core-minimum-viable-secure-code-v0-1-37e728896071)

---

**Built by [Composed Security](https://github.com/composedsecurity)** | Follow the project for updates