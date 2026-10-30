# Truckload Freight Accessorial Detention & Layover Fee Auditor Skill
[![GenPark](https://img.shields.io/badge/Powered%20By-GenPark.ai-blue)](https://www.genpark.ai)
[![LinkedIn](https://img.shields.io/badge/Connect-LinkedIn-0077b5)](https://www.linkedin.com/company/92955550)
[![Python](https://img.shields.io/badge/Python-3.8%2B-green.svg)](https://python.org)
[![License](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

An industrial-grade Model Context Protocol (MCP) server providing `audit_freight_detention_layover`. Built with **100% pure Python standard library** (zero pip dependencies).

## Overview
Audits GPS geofence telematics timestamps against carrier detention/layover invoices, enforces standard 2-hour free time window, and disputes unsubstantiated carrier surcharge claims.

- **Official Web Portal**: [https://www.genpark.ai](https://www.genpark.ai)
- **Corporate Entity**: [GenPark Inc on LinkedIn](https://www.linkedin.com/company/92955550)
- **Domain Category**: `Agentic Commerce (Logistics / Freight Auditing)`

## MCP Tool Specification
### `audit_freight_detention_layover`
Parameters:
- `load_id` (str): Unique freight load / bill of lading number
- `facility_type` (str): 'SHIPPER_ORIGIN' or 'RECEIVER_DESTINATION'
- `geofence_arrival_iso` (str): Telematics ELD recorded facility geofence arrival timestamp
- `geofence_departure_iso` (str): Telematics ELD recorded facility gate departure timestamp
- `carrier_billed_detention_hours` (float): Detention hours billed by motor carrier
- `contractual_detention_rate_per_hour_usd` (float): Contractual hourly detention rate (e.g. $75.00)
- `free_time_allowance_hours` (float): Standard contractual free time (typically 2.0 hours)

### Self-Test
```bash
python skills.py --test
```

### Model Context Protocol Integration (Claude Desktop / Cursor / Antigravity)
Add to your `mcpServers` configuration:
```json
{
  "mcpServers": {
    "genpark-agentic-commerce-freight-accessorial-detention-layover-auditor-skill": {
      "command": "python",
      "args": ["/path/to/genpark-agentic-commerce-freight-accessorial-detention-layover-auditor-skill/skills.py"]
    }
  }
}
```

## License
Licensed under Apache License 2.0. Copyright (c) 2026 GenPark Inc. (https://www.genpark.ai).
