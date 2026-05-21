---
name: molsci-skills
description: |
  Use when querying pharmaceutical, chemical, or life science data via the molsci-openapi tool. Covers drug R&D, clinical trials, patents, chemical properties, spectra, synthesis, medical literature, and related domains.

  Triggers: pharma API, npx molsci-openapi, drug data, clinical data, chemical data, life science query.

  触发词: 医药数据、化学数据、临床数据、药品查询、分子性质、谱图查询。
---

# Molsci OpenAPI CLI

Call the Molsci General API via `npx molsci-openapi` to query pharmaceutical and chemical data across multiple modules.

**Architecture**: `npx molsci-openapi` → HTTP POST → Molsci General API

**Module routing**: See [references/routing.md](references/routing.md) to determine which module's API list to load based on the user's query intent. Then read the corresponding `references/<module>/api-list.md` for available RPC names and parameters.

## 1. Prerequisites

### 1.1 Node.js

Node.js >= 18 required. Verify:

```bash
node --version
```

### 1.2 molsci-openapi

No installation needed — `npx` downloads and runs the latest version automatically:

```bash
npx molsci-openapi --help
```

## 2. Authentication

### 2.1 Security rules (mandatory)

- **NEVER** read, echo, or print the API key value.
- **NEVER** prompt the user to paste their API key in the chat.
- **NEVER** embed the API key in scripts or command output.
- **ONLY** use `molsci-openapi configure` (interactive, key input is masked) or environment variables the user has set in their local shell.

> **If the user provides an API key in chat:**
> 1. Stop immediately.
> 2. Guide them to run `npx molsci-openapi configure` in their own terminal.
> 3. Resume only after configuration is confirmed.

### 2.2 Configure credentials

Interactive setup (recommended — API key input is masked):

```bash
npx molsci-openapi configure
```

This saves to `~/.molsci-openapi/config.json` with `600` permissions.

### 2.3 Environment variables (optional)

Override config file (highest priority):

```bash
export PHARMA_BASE_URL=https://your-api.example.com
export PHARMA_API_KEY=your-api-key
```

### 2.4 Credential priority

1. **Environment variables** — `PHARMA_BASE_URL`, `PHARMA_API_KEY`
2. **Config file** — `~/.molsci-openapi/config.json`

### 2.5 Verify credentials

```bash
npx molsci-openapi CenterPurchaseList --data '{"page":1,"size":1}'
```

A successful response returns JSON data. Common errors:

| Status | Cause | Fix |
|---|---|---|
| `HTTP 401` | Invalid API key | Run `npx molsci-openapi configure` to update |
| `HTTP 404` | Wrong base URL | Check `PHARMA_BASE_URL` or config file |
| `Request failed: fetch failed` | Cannot reach server | Check network, proxy, and base URL |

## 3. Usage

### Command format

```bash
npx molsci-openapi <RpcName> --data '<json>'
```

- `<RpcName>` — the RPC method name (e.g. `GlobalDrugDevList`)
- `--data` — JSON string matching the API's request parameters. **Before constructing `--data`, locate the target RPC in the module's api-list, then check that same module's `api.swagger.json` for parameter names, types, and descriptions.**

### Examples

```bash
# Query global drug R&D pipeline
npx molsci-openapi GlobalDrugDevList --data '{"page":1,"size":10}'

# Look up drug approvals
npx molsci-openapi CnDrugApprovalList --data '{"page":1,"size":10,"keyword":"阿莫西林"}'

# Search clinical trials
npx molsci-openapi CnClinicalTrialList --data '{"page":1,"size":10,"drug_name":"remdesivir"}'

# Chemical property query (tqsk module)
npx molsci-openapi PropDetail --data '{"codes":["64-17-5"]}'

# Spectra search (tqsk module)
npx molsci-openapi SpectraSearch --data '{"page":1,"size":10}'
```

### Usage patterns

**List → Detail**: Most domains have a `List`/`Search` endpoint for searching/pagination and detail endpoints keyed by specific IDs. Typical workflow:

```bash
# 1. Search by keyword to get the target record
npx molsci-openapi CnDrugApprovalList --data '{"keyword":"阿莫西林","page":1,"size":10}'
# Response includes approval_number, drug_name, etc.

# 2. Use IDs from the list result to query detail endpoints
npx molsci-openapi CnDrugApprovalBaseInfo --data '{"approval_number":"国药准字H20163436"}'
npx molsci-openapi CnDrugApprovalMedicalInsuranceStatus --data '{"approval_number":"国药准字H20163436"}'
```

**Pagination**: All List/Search endpoints support `{"page":1,"size":10}`. Responses include a `total` field for total record count.

### Common mistakes

```bash
# Wrong: missing --data
npx molsci-openapi GlobalDrugDevList

# Wrong: using = instead of space for --data
npx molsci-openapi GlobalDrugDevList --data='{"page":1}'

# Wrong: curl-ing the API directly (use molsci-openapi)
curl -X POST https://api.example.com/pharma/general/v1/global_drug_dev/list

# Wrong: missing npx (molsci-openapi is not globally installed)
molsci-openapi GlobalDrugDevList --data '{}'

# Wrong: passing API key in chat or command line
npx molsci-openapi GlobalDrugDevList --data '{}' -H "Authorization: Bearer sk-xxx"
```

## 4. References

- [references/routing.md](references/routing.md) — Maps query intent to the correct API module and its api-list + swagger spec