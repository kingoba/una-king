# ioChurch Core Module — `trackone/iochurch`

Foundational module for the ioChurch suite. Provides:
- Church / Campus / Fund database schema
- Organization opt-in linkage
- Membership mapping
- Alert-driven automation
- JS toggle form and admin dashboards

## 📦 Install

1. Copy the module to:  
   `modules/trackone/iochurch/`

2. Install via Studio → Apps Market → **Downloaded** tab.

3. Visit Studio → Pages → **Organizations**  
   Add the block:  
   - Type: Service  
   - Module: `iochurch`  
   - Method: `serviceOrgToggleBlock`  
   - Params: `=profile_id=`

## 🚦 Features

- Opt-in: Organizations can enable ioChurch features
- Dashboard-ready: metrics, membership, giving, etc.
- Role-aware: supports volunteers, staff, admins
- Extensible via alerts

## 🛠️ Services

- `servicePing()`
- `serviceOrgToggleBlock($iOrgProfileId)`
- `serviceGetChurch($id)`
- `serviceListChurches($status = null)`
- `serviceListCampuses($churchId)`
- `serviceListFunds($churchId)`
- `serviceCreateChurchFromOrg($aOrg, $iActor)`

## ⚙️ Tables

- `mod_iochurch_churches`
- `mod_iochurch_member_church`
- `mod_iochurch_org_bindings`
- (legacy) `to_iochurch_campuses`
- (legacy) `to_iochurch_funds`

## 🔔 Alerts

Registered via `enable.sql`:
- `profile: join` → triggers church membership sync
- `organization: added` → optional auto-create church

## 🔐 Permissions

- Site admins can manage all
- Organization owners or administrators (via connection or service) can toggle
- ACL actions:
  - `manage_churches`
  - `manage_campuses`
  - `manage_funds`

## 🧪 Version

- `1.0.1` — Opt-in toggle system, alerts, dashboard scaffolding
