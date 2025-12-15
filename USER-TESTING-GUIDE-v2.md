# RailScanPro – Unified Test Strategy & Test Cases

## 1. Purpose

This document defines a **single source of truth** for testing RailScanPro across:
- Quality Assurance (QA)
- Development (Dev)
- Investors
- Auditors / Compliance

Each section provides a **targeted view** of the same system, focused on the risks and concerns of that audience.

---

## 2. Test Scope

### In Scope
- Authentication & user lifecycle
- Inventory management (manual + AI-assisted)
- AI photo scanning and overrides
- Valuation & insurance reporting
- Data export (CSV, PDF, JMRI)
- Subscription & billing (Stripe)
- Clubs, museums, and multi-user access
- Security, privacy, and performance

### Out of Scope
- Third-party AI model internals
- Stripe internal processing
- External valuation provider uptime

---

## 3. Test Environments

| Environment | Purpose |
|------------|--------|
| Local / Dev | Unit & integration testing |
| Staging | QA, regression, performance |
| Production | Smoke tests only |

---

## 4. Test Types

| Type | Description |
|----|------------|
| Smoke | Release blockers |
| Functional | Feature correctness |
| Regression | Prevent breakage |
| AI Validation | Accuracy & fallback |
| Security | Access & isolation |
| Performance | Scale & latency |
| Compliance | Data handling |

---

# 5. QA Test Suite

## 5.1 Smoke Tests

| ID | Description | Expected Result |
|---|------------|----------------|
| SMK-001 | User login | Dashboard loads |
| SMK-002 | Manual inventory add | Item saved |
| SMK-003 | AI scan upload | Item created |
| SMK-004 | CSV export | File downloads |
| SMK-005 | Paid feature access | Allowed |

---

## 5.2 Functional Tests

### Authentication

| ID | Priority | Description | Expected |
|----|----------|------------|----------|
| AUTH-001 | High | Sign up | Account created |
| AUTH-002 | High | Login | Redirect to dashboard |
| AUTH-003 | Medium | Password reset | Email sent |

### Inventory

| ID | Priority | Description | Expected |
|----|----------|------------|----------|
| INV-001 | High | Manual item entry | Saved |
| INV-002 | Medium | Edit item | Persisted |
| INV-003 | Medium | Delete item | Removed |
| INV-004 | Medium | Filter inventory | Correct list |

### AI Photo Scanning

| ID | Priority | Description | Expected |
|----|----------|------------|----------|
| AI-001 | High | Upload clear image | Scan starts |
| AI-002 | High | Detect model | Fields populated |
| AI-003 | Medium | Confidence score shown | Visible |
| AI-004 | High | Manual override | Saved |
| AI-005 | Medium | Bad image handling | Error shown |

### Valuation & Insurance

| ID | Priority | Description | Expected |
|----|----------|------------|----------|
| VAL-001 | High | Show valuation | Value visible |
| VAL-002 | Medium | Generate insurance PDF | PDF created |

### Export

| ID | Priority | Description | Expected |
|----|----------|------------|----------|
| EXP-001 | High | CSV export | Correct data |
| EXP-002 | Medium | PDF export | Formatted |
| EXP-003 | Medium | JMRI export | Imports |

---

# 6. Dev Test Suite

## 6.1 Unit Tests
- Inventory CRUD logic
- AI scan mapping
- Valuation calculations
- Subscription entitlement checks

## 6.2 Integration Tests

| ID | Scenario | Expected |
|----|---------|----------|
| DEV-INT-001 | API ↔ DB | Data persisted |
| DEV-INT-002 | AI ↔ Inventory | Item created |
| DEV-INT-003 | Stripe webhook | No double billing |

## 6.3 Failure Injection

| ID | Scenario | Expected |
|----|---------|----------|
| DEV-FI-001 | AI timeout | Graceful error |
| DEV-FI-002 | DB disconnect | User-safe error |
| DEV-FI-003 | Stripe delay | Idempotent handling |

## 6.4 Observability

| Area | Expected |
|----|---------|
| Logging | Traceable errors |
| Metrics | AI latency tracked |
| Alerts | Billing failures trigger alert |

---

# 7. Investor Validation Suite

## 7.1 Product Maturity

| Metric | Target |
|------|-------|
| Smoke pass rate | ≥ 99% |
| Critical bugs | 0 |

## 7.2 Scalability

| Scenario | Expected |
|--------|---------|
| 10k inventory items | < 5s load |
| 100 concurrent users | No errors |

## 7.3 AI Differentiation

| Test | Expected |
|----|---------|
| AI accuracy benchmark | Documented |
| Override rate | Measured |

## 7.4 Revenue Protection

| Test | Expected |
|----|---------|
| Free vs paid access | Enforced |
| Billing failures | No data loss |

---

# 8. Auditor / Compliance Suite

## 8.1 Data Privacy & Ownership

| ID | Description | Expected |
|----|-------------|----------|
| AUD-001 | Export all user data | Complete export |
| AUD-002 | Account deletion | Data removed |
| AUD-003 | Image access control | Auth required |

## 8.2 Access Control

| Test | Expected |
|----|---------|
| Cross-user access | Denied |
| Role enforcement | Enforced |

## 8.3 Audit Trails

| Event | Expected |
|-----|---------|
| Inventory deletion | Logged |
| Subscription change | Logged |

## 8.4 Secure Storage

| Area | Expected |
|----|---------|
| HTTPS | Enforced |
| Encryption at rest | Documented |

---

# 9. Performance Benchmarks

| Area | Target |
|----|-------|
| Dashboard load | < 3s |
| Inventory (5k items) | < 5s |
| AI scan queue | < 60s |

---

# 10. Entry / Exit Criteria

### Entry
- Code merged
- Test env stable

### Exit
- All smoke tests pass
- No open critical defects
- Regression ≥ 95% pass

---

# 11. Traceability Matrix

| Feature | QA | Dev | Investor | Auditor |
|-------|----|----|----------|---------|
| AI Scan | AI-001 | DEV-FI-001 | Accuracy metric | AUD-003 |
| Billing | BILL-001 | DEV-INT-003 | Revenue protection | AUD-002 |
| Inventory | INV-001 | Unit tests | Scalability | AUD-001 |
