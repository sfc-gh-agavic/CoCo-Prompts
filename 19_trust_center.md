# Demo 19: Trust Center (~5 min)

## What You'll Show

Cortex Code can query Snowflake's Trust Center to review security findings, check scanner status, assess severity distribution, and get remediation guidance — all from conversational prompts.

## Context for Presenter

Snowflake Trust Center provides automated security scanning and findings for your account. It covers CIS benchmarks, security essentials, and threat intelligence. Most customers don't regularly check Trust Center — Cortex Code makes it easy to get a security posture overview.

**Key talking points:**
- Trust Center runs automated security scanners against your account
- Findings are categorized by severity (critical, high, medium, low)
- CIS benchmarks provide industry-standard security assessment
- Cortex Code summarizes findings and provides remediation guidance

---

## Prompts to Execute

### 1. View security findings

```
Show me the current security findings from the Snowflake Trust Center. How many findings are there and what's the severity breakdown?
```

**What to highlight:** Cortex Code queries Trust Center metadata and presents a clear summary of the security posture — critical and high findings are flagged prominently.

---

### 2. Check scanner status

```
What security scanners are currently enabled in the Trust Center? Are they all running on schedule? Show me the last scan time for each.
```

**What to highlight:** Scanner management — ensuring all relevant scanners are active and running on schedule.

---

### 3. CIS benchmark results

```
Show me the CIS benchmark results from Trust Center. Which checks are passing and which are failing? Focus on any critical or high severity failures.
```

**What to highlight:** CIS benchmarks are industry-standard security controls — this shows compliance status at a glance.

---

### 4. Remediation guidance

```
For the highest severity findings in Trust Center, give me remediation guidance. What specific actions should I take to address the most critical security issues?
```

**What to highlight:** Cortex Code doesn't just show problems — it provides actionable remediation steps, making it practical for security teams to act on findings.

---

## Expected Outcome

The audience sees that Snowflake Trust Center provides comprehensive security monitoring, and Cortex Code makes it accessible without navigating multiple UI screens.
