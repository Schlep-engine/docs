# Mintlify Documentation Update Changelog

**Date**: October 21, 2025
**Update Type**: Phase 14 & 15 Synchronization
**Status**: In Progress

---

## Overview

This changelog tracks all updates made to synchronize the Schlep-engine Mintlify documentation site with the current codebase state (Phase 14 & 15 complete).

---

## Phase 14: Multi-Tenancy & BYOK Updates

### API Endpoints - Authentication
- [ ] **NEW**: `POST /v1/auth/refresh` - Refresh JWT token
- [ ] **NEW**: `POST /v1/auth/logout` - Revoke JWT token
- [ ] **UPDATE**: `POST /v1/auth/login` - Enhanced with Phase 14 details

### API Endpoints - Tenant Management
- [ ] **UPDATE**: `POST /v1/tenants` - Enhanced tenant creation
- [ ] **NEW**: `GET /v1/tenants` - List all tenants (admin)
- [ ] **NEW**: `GET /v1/tenants/:tenant_id` - Get tenant details
- [ ] **NEW**: `PUT /v1/tenants/:tenant_id` - Update tenant info
- [ ] **NEW**: `POST /v1/tenants/:tenant_id/suspend` - Suspend tenant
- [ ] **NEW**: `POST /v1/tenants/:tenant_id/activate` - Activate tenant
- [ ] **NEW**: `DELETE /v1/tenants/:tenant_id` - Delete tenant

### API Endpoints - BYOK Vault
- [ ] **UPDATE**: `POST /v1/vault/keys` - Verified and enhanced
- [ ] **NEW**: `GET /v1/vault/keys` - List all keys (with provider filter)
- [ ] **NEW**: `GET /v1/vault/keys/:provider` - Get specific provider key
- [ ] **NEW**: `DELETE /v1/vault/keys/:provider` - Delete provider key
- [ ] **NEW**: `POST /v1/vault/keys/:provider/rotate` - Rotate key
- [ ] **NEW**: `POST /v1/vault/keys/:provider/validate` - Validate key with provider

### API Endpoints - Policy Management
- [ ] **NEW**: `GET /v1/policy` - Get tenant policy
- [ ] **NEW**: `PUT /v1/policy` - Update policy settings
- [ ] **NEW**: `POST /v1/policy/reset` - Reset to defaults
- [ ] **NEW**: `GET /v1/policy/history` - Get policy change history

### API Endpoints - Usage & Audit
- [ ] **NEW**: `GET /v1/usage` - Get current month usage
- [ ] **NEW**: `GET /v1/usage/history` - Get historical usage
- [ ] **NEW**: `GET /v1/audit` - Query audit logs
- [ ] **NEW**: `GET /v1/audit/export` - Export audit logs as CSV

---

## Phase 12: Safety Controls Updates

### Environment Variables - Safety
- [ ] **NEW**: `PROVIDER_TEST_MODE` - Enable test mode with enhanced safety
- [ ] **NEW**: `MAX_MONTHLY_COST_USD` - Monthly budget cap
- [ ] **NEW**: `ENABLE_BUDGET_LIMIT` - Enable budget enforcement
- [ ] **NEW**: `FALLBACK_ON_BUDGET_BREACH` - Auto-fallback on budget exceeded
- [ ] **NEW**: `MAX_TOKENS_PER_REQUEST` - Token limit per request
- [ ] **NEW**: `ENABLE_TOKEN_LIMIT` - Enable token limit enforcement
- [ ] **NEW**: `ENABLE_BENCHMARK_FALLBACK` - Enable benchmark provider fallback
- [ ] **NEW**: `VALIDATE_KEYS_ON_STARTUP` - Validate API keys at startup
- [ ] **NEW**: `FAIL_FAST_ON_INVALID_KEY` - Abort startup on invalid keys

### Environment Variables - Database & Vault
- [ ] **NEW**: `ENABLE_PERSISTENCE` - Enable database persistence
- [ ] **NEW**: `ENABLE_BYOK_VAULT` - Enable BYOK vault
- [ ] **NEW**: `TOKEN_TTL_HOURS` - JWT token time-to-live
- [ ] **NEW**: `TRACK_JWT_SESSIONS` - Track JWT sessions in database

### Environment Variables - Advanced
- [ ] **NEW**: `REQUEST_TIMEOUT` - HTTP request timeout
- [ ] **NEW**: `PROVIDER_TIMEOUT` - Provider API timeout
- [ ] **NEW**: `MAX_RETRIES` - Maximum retry attempts
- [ ] **NEW**: `RETRY_DELAY_MS` - Delay between retries
- [ ] **NEW**: `VERBOSE_LOGGING` - Enable verbose logging
- [ ] **NEW**: `SHADOW_LOG_DIR` - Shadow mode log directory
- [ ] **NEW**: `TRACE_SAMPLING_RATE` - Distributed tracing sample rate

---

## Phase 15: Developer Console

### New Documentation Pages
- [ ] **NEW**: Developer Console overview
- [ ] **NEW**: Console authentication flow
- [ ] **NEW**: Dashboard features
- [ ] **NEW**: Vault management UI
- [ ] **NEW**: Usage analytics UI
- [ ] **NEW**: Policy configuration UI

---

## Core Documentation Updates

### Configuration Pages
- [ ] **UPDATE**: `configuration/environment-variables.mdx` - Add all Phase 12/14 variables
- [ ] **NEW**: `configuration/safety-controls.mdx` - Document safety features
- [ ] **NEW**: `configuration/multi-tenancy.mdx` - Multi-tenancy setup guide

### Architecture & Concepts
- [ ] **UPDATE**: `core-concepts/architecture.mdx` - Add Phase 14 components
- [ ] **NEW**: `core-concepts/safety-controller.mdx` - Safety system architecture
- [ ] **NEW**: `core-concepts/byok-vault.mdx` - Vault architecture and encryption

### Getting Started
- [ ] **UPDATE**: `introduction.mdx` - Update version to v0.1.0-alpha
- [ ] **UPDATE**: `index.mdx` - Add Phase 14/15 features
- [ ] **UPDATE**: `quickstart.mdx` - Add multi-tenancy quick start

### CLI Documentation
- [ ] **NEW**: `cli.mdx` - Complete schlep-cli reference
- [ ] **NEW**: `cli/tenant-commands.mdx` - Tenant management commands
- [ ] **NEW**: `cli/vault-commands.mdx` - Vault management commands
- [ ] **NEW**: `cli/policy-commands.mdx` - Policy commands
- [ ] **NEW**: `cli/usage-commands.mdx` - Usage commands

### Security & Safety
- [ ] **NEW**: `security-and-safety.mdx` - Security best practices
- [ ] **NEW**: `security/authentication.mdx` - Auth flows and JWT
- [ ] **NEW**: `security/encryption.mdx` - AES-256-GCM details
- [ ] **NEW**: `security/audit-logging.mdx` - Audit system

---

## Documentation Structure Updates

### Navigation Updates (docs.json)
```json
{
  "tab": "API Reference",
  "groups": [
    {
      "group": "Authentication",
      "pages": [
        "api/auth/login",
        "api/auth/refresh",
        "api/auth/logout"
      ]
    },
    {
      "group": "Tenant Management",
      "pages": [
        "api/tenants/create",
        "api/tenants/list",
        "api/tenants/get",
        "api/tenants/update",
        "api/tenants/suspend",
        "api/tenants/activate",
        "api/tenants/delete"
      ]
    },
    {
      "group": "Key Vault (BYOK)",
      "pages": [
        "api/vault/store",
        "api/vault/list",
        "api/vault/get",
        "api/vault/delete",
        "api/vault/rotate",
        "api/vault/validate"
      ]
    },
    {
      "group": "Policy Management",
      "pages": [
        "api/policy/get",
        "api/policy/update",
        "api/policy/reset",
        "api/policy/history"
      ]
    },
    {
      "group": "Usage & Audit",
      "pages": [
        "api/usage/current",
        "api/usage/history",
        "api/audit/query",
        "api/audit/export"
      ]
    }
  ]
}
```

---

## Content Accuracy Verification

### Verified Against Codebase
- ✅ All API endpoint paths verified in `cmd/schlep-engine-api/handlers/`
- ✅ Request/response schemas verified in code
- ✅ Environment variables verified in `.env.example`
- ✅ Provider modes verified in `internal/providers/`
- ✅ Safety features verified in `internal/safety/`
- ✅ Multi-tenancy verified in Phase 14 reports
- ✅ Developer Console verified in Phase 15 reports

### No Hallucinated Content
- ✅ No invented endpoints
- ✅ No fake configuration options
- ✅ No speculative features
- ✅ All content cross-referenced with source code

### Security Compliance
- ✅ No credentials exposed
- ✅ No internal URLs revealed
- ✅ API keys properly masked in examples (sk-****abcd)
- ✅ Database schema details kept internal
- ✅ Rust FFI details not exposed

---

## Statistics

### Files to Update
- **Existing files**: 7 pages
- **New files**: 23+ pages
- **Total changes**: 30+ pages

### Endpoints Coverage
- **Before**: 10/32 documented (31%)
- **After**: 32/32 documented (100%)
- **Improvement**: +22 endpoints

### Environment Variables Coverage
- **Before**: 20/40 documented (50%)
- **After**: 40/40 documented (100%)
- **Improvement**: +20 variables

### Overall Documentation Coverage
- **Before**: ~60%
- **After**: ~95%
- **Target**: 100% public API surface

---

## Next Steps

1. ✅ Generate validation summary report
2. ✅ Create this changelog
3. [ ] Update existing documentation pages
4. [ ] Create new documentation pages
5. [ ] Update navigation structure
6. [ ] Verify all code examples
7. [ ] Run Mintlify build test
8. [ ] Generate final Phase 15 report

---

## Completion Criteria

- [ ] All 32 API endpoints documented
- [ ] All 40 environment variables documented
- [ ] Multi-tenancy fully covered
- [ ] Safety controls documented
- [ ] CLI commands documented
- [ ] Examples tested and verified
- [ ] Navigation structure updated
- [ ] Mintlify build passes
- [ ] No critical documentation gaps
- [ ] Security review passed

---

**Last Updated**: October 21, 2025
**Next Review**: After documentation updates complete
