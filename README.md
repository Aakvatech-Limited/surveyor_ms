# Surveyor Management System

## Business Summary

Surveyor Management System is a Frappe app for managing insurance survey work from insurer appointment through assignment, site inspection, reporting, follow-up, dispute handling, and fee note tracking.

The app is designed for surveyor operations teams that need one structured place to record insurers, surveyors, claim assignments, inspection evidence, assessment details, recommendations, and billing-related fee notes. It replaces scattered spreadsheets, emails, and manual registers with linked Frappe records.

Repository evidence shows this as a standalone Frappe app. It includes ERPNext-style reference fields such as customer, employee, supplier, and sales invoice references, but it does not define ERPNext as a required dependency and does not currently create or update ERPNext documents automatically.

## Business Problems This App Solves

| Problem | How the app helps |
|---|---|
| Survey assignments are tracked manually | Provides a central `Survey Assignment` record with insurer, surveyor, claim, loss, SLA, assessment, and document checklist fields. |
| Surveyor and insurer information is scattered | Provides `Insurer Master` and `Surveyor Profile` masters with contact, billing, specialization, and empanelment details. |
| Site inspection details are hard to audit | Captures site inspection logs, GPS coordinates, witnesses, pending items, and inspection photos. |
| Report preparation lacks a consistent record | Provides `Survey Report` records for preliminary, final, re-survey, and supplementary reports. |
| Follow-ups are easy to lose | Provides submittable `Follow-up Log` records for document requests, site visit follow-ups, insurer queries, and payment follow-ups. |
| Fee notes are disconnected from assignments | Provides `Fee Note` and `Fee Note Item` records linked back to survey assignments and surveyors. |
| Disputes and repudiation cases need visibility | Provides a `Repudiation Register` with dispute type, disputed amounts, position, resolution, escalation, ombudsman, and court fields. |

## Who This App Is For

| Audience | Fit |
|---|---|
| Insurance survey firms | Good fit for teams handling claim survey assignments and inspections. |
| Loss assessment teams | Useful where assessed amounts, salvage, depreciation, and recommendations need structured records. |
| Operations managers | Useful for tracking status, SLA dates, document gaps, follow-ups, and fee notes. |
| Frappe implementers | Useful as a base app for a custom surveyor operations workflow. |

## Who This App Is Not For

| Audience | Why it may not fit yet |
|---|---|
| Teams needing automatic ERPNext accounting integration | Current ERPNext-related fields are reference-style fields; no Sales Invoice creation or accounting automation is implemented. |
| Teams needing advanced reporting out of the box | No query reports, script reports, dashboards, or number cards are included in the repository. |
| Teams needing custom approval workflows | No workflow fixtures or role-specific approval logic are included yet. |
| Teams needing mobile-first offline inspections | The repository does not include a mobile app, offline sync, or field inspection UI beyond standard Frappe forms. |

## Business Benefits

| Benefit | Business Impact |
|---|---|
| Centralized survey records | Reduces duplicate registers and gives teams a single operational trail. |
| Linked assignment lifecycle | Connects assignment, inspection, report, follow-up, dispute, and fee records. |
| Structured assessment data | Captures claimed amount, assessed amount, depreciation, salvage, and net payable values. |
| Better follow-up control | Due dates, action owners, statuses, and resolutions can be tracked formally. |
| Operational visibility | Workspace shortcuts and DocType lists help users find core work quickly. |
| Audit-friendly history | Major DocTypes have change tracking enabled. |

## Before and After

| Before | After |
|---|---|
| Assignment details are kept in spreadsheets or email threads. | Assignment details are stored in a structured `Survey Assignment` record. |
| Inspection notes, witnesses, and photos are stored separately. | Inspection evidence is grouped in `Site Inspection Log` with child tables. |
| Report decisions are hard to trace back to assignment data. | `Survey Report` links to the assignment and fetches key context fields. |
| Follow-ups depend on memory or informal reminders. | `Follow-up Log` records due dates, type, status, owner, and resolution. |
| Fee notes are prepared outside the operational record. | `Fee Note` links billing information back to the survey assignment. |

## Typical Use Cases

| Use Case | Supported By |
|---|---|
| Register an insurer and its SLA or fee preferences | `Insurer Master` |
| Maintain surveyor records, specializations, and empanelments | `Surveyor Profile`, `Surveyor Specialisation`, `Surveyor Empanelment` |
| Create and track a claim survey assignment | `Survey Assignment` |
| Record claimed and assessed loss items | `Claim Loss Item` child table |
| Track required and received claim documents | `Required Document Checklist` child table |
| Log site visits with witnesses and photos | `Site Inspection Log`, `Inspection Witness`, `Inspection Photo` |
| Prepare survey report records and recommendations | `Survey Report` |
| Record disputes or repudiation-related cases | `Repudiation Register` |
| Generate and track fee notes | `Fee Note`, `Fee Note Item` |
| Track document, insurer, site visit, or payment follow-ups | `Follow-up Log` |

## Example Business Workflow

1. An operations user creates an insurer in `Insurer Master`.
2. A surveyor profile is created with specializations and insurer empanelment details.
3. A new `Survey Assignment` is opened for an insurer appointment or claim.
4. The team records claim details, insured contact details, loss location, due dates, required documents, and loss items.
5. A site visit is recorded in `Site Inspection Log`, including witnesses, coordinates, notes, pending items, and photos.
6. Follow-ups are logged for missing documents, insurer queries, payment issues, or site visit actions.
7. A `Survey Report` is created and linked to the assignment with recommendation and financial summary details.
8. If a dispute arises, the team tracks it in `Repudiation Register`.
9. A `Fee Note` is prepared and linked to the assignment for billing follow-up.

## Stand-alone Value

The app can provide value in a Frappe-only environment by defining the surveyor operation records, workspace navigation, permissions, naming series, field dependencies, attachments, and change tracking needed to run the process.

It does not require ERPNext according to the current metadata. The app can therefore act as a dedicated operations layer for insurance survey work even when ERPNext accounting, stock, HR, or CRM modules are not installed.

## ERPNext Value Addition

ERPNext integration appears optional and reference-only in the current repository.

| ERPNext-related concept | Current evidence |
|---|---|
| Customer | `Insurer Master` has an `ERPNext Customer` data field. |
| Employee | `Surveyor Profile` has an `ERPNext Employee` data field. |
| Supplier | `Surveyor Profile` has an `ERPNext Supplier` data field. |
| Sales Invoice | `Fee Note` has a `Sales Invoice` data field. |
| Project | `Survey Assignment` has a `Project` data field. |

No repository evidence was found for automatic ERPNext document creation, mapped documents, custom fields on ERPNext DocTypes, document event hooks, or whitelisted API calls.

## Decision Guide

| Question | Yes / No |
|---|---|
| Do you track survey assignments manually today? | |
| Do you need a central register for insurers, surveyors, assignments, inspections, reports, disputes, and fee notes? | |
| Do you need structured assessment fields for claimed, assessed, depreciation, salvage, and net payable values? | |
| Do you need to track document requests, insurer queries, site follow-ups, or payment follow-ups? | |
| Do you need standard Frappe forms first, with custom automation added later? | |
| Do you need immediate ERPNext accounting automation? | |

## Expected Business Outcomes

The app can help improve assignment visibility, record completeness, inspection evidence management, follow-up control, and billing traceability. Actual operational outcomes will depend on configuration, user adoption, reporting needs, data quality, and any custom automation added during implementation.

## Screenshots / Visual Walkthrough

Screenshots are not included in this repository.

Suggested screenshots before publishing:

- Surveyor Management System workspace
- Survey Assignment form
- Site Inspection Log form with witnesses and photos
- Survey Report form
- Fee Note form
- Repudiation Register form

## Demo Scenario

1. Create an active insurer with SLA and fee settings.
2. Create a surveyor profile with specializations and empanelled insurers.
3. Create a survey assignment for a fire, motor, marine, engineering, or miscellaneous claim.
4. Add claimed loss items and required documents.
5. Record a site inspection with GPS coordinates, witnesses, and photos.
6. Create a preliminary or final survey report.
7. Add follow-ups for missing documents or insurer queries.
8. Create a fee note and update payment status.

## Implementation Effort

| Area | Effort | Notes |
|---|---|---|
| Frappe app installation | Low | Standard bench install once a compatible Frappe site is ready. |
| Master data setup | Medium | Insurers, surveyors, specializations, empanelments, and fee preferences should be prepared. |
| Workflow alignment | Medium | Status values and operating process should be confirmed with the business team. |
| ERPNext integration | High if required | Current repository does not automate ERPNext document creation or linking. |
| Reports and dashboards | Medium | Workspace links exist, but custom reports and dashboards are not included yet. |
| Data migration | Depends | Spreadsheet migration is possible through Frappe tools but must be mapped and validated. |
| Training | Medium | Users need to understand assignment, inspection, report, follow-up, dispute, and fee note flows. |

## What Needs to Be Ready Before Implementation

- Frappe bench and site access.
- Agreed claim survey workflow and status definitions.
- Insurer master data.
- Surveyor master data, specializations, and empanelment details.
- Required document checklist patterns.
- SLA rules for preliminary and final reports.
- Fee calculation rules and billing ownership.
- Any ERPNext integration requirements, if accounting or HR links are expected.
- Reporting requirements for managers and operations users.

## Risks and Considerations

| Risk | Consideration |
|---|---|
| ERPNext expectations may be higher than current code | Current ERPNext fields are data references, not automated integrations. |
| Reports are not yet defined | Management dashboards or MIS reports may need to be added. |
| Permissions are broad | Current DocType permissions are mostly for `System Manager`; production roles should be designed. |
| Business rules are not enforced in Python controllers | Controllers are currently minimal, so validation and automation should be added where needed. |
| License file has placeholder copyright text | `license.txt` should be updated with the correct year and copyright holder. |
| Python version is very new | `pyproject.toml` and CI target Python 3.14; confirm compatibility with the target Frappe version and deployment stack. |

## Frequently Asked Business Questions

### Do we need ERPNext?

No hard ERPNext dependency is defined in the repository. The app appears to require Frappe and can run as a standalone Frappe app.

### Will this replace ERPNext?

No. It is an operational survey management app. If ERPNext is used for accounting, HR, CRM, or invoicing, integration work may be needed.

### Can it be customized?

Yes. It is a Frappe app with DocTypes, controllers, workspace configuration, and standard app hooks that can be extended.

### Can managers get reports?

The data model supports reporting, but custom report definitions are not included yet. Reports should be added based on management requirements.

### Can existing spreadsheet data be migrated?

Likely yes through Frappe import tools or custom migration scripts, but field mapping, validation, and cleaning must be planned.

### What should we prepare first?

Prepare insurer data, surveyor data, assignment statuses, SLA rules, fee rules, document checklist templates, and reporting requirements.

---

## Key Features

- Survey assignment register with insurer, surveyor, claim, policy, loss, SLA, assessment, and document checklist fields.
- Insurer master with contact details, SLA settings, fee settings, and ERPNext customer reference.
- Surveyor profile with license or registration number, contact details, specializations, empanelled insurers, and ERPNext employee or supplier references.
- Site inspection logs with location, GPS coordinates, inspection type, notes, witnesses, photos, pending items, and next visit date.
- Survey reports with report type, assignment context, loss details, assessed items, recommendation, basis of recommendation, financial summary, and PDF attachment.
- Appointment letters linked to assignments, insurers, surveyors, insured contacts, proposed visit details, and delivery status.
- Submittable follow-up logs with due date, action owner, resolution notes, and amendment support.
- Repudiation and dispute register with dispute type, amounts, position, resolution, ombudsman, and court escalation fields.
- Fee notes with fee calculation mode, fee line items, totals, sales invoice reference, and payment status.
- Desk workspace with shortcuts and cards for operations, masters, and resolution records.

## Compatibility

| Component | Current repository evidence |
|---|---|
| Frappe | Required by app structure and imports, but exact supported Frappe version is not declared. |
| ERPNext | Not declared as a required app. ERPNext references are optional data fields. |
| Python | `pyproject.toml` requires Python `>=3.14`; CI uses Python 3.14. |
| Node | CI uses Node 24. |
| Database | CI uses MariaDB 11.8. |
| Redis | CI uses Redis services for cache and queue. |
| App version | `surveyor_ms/__init__.py` defines `0.0.1`. |

## App Mode

`Standalone Frappe app`

ERPNext support appears optional and reference-only. No `required_apps`, ERPNext imports, ERPNext hooks, fixtures, or mapped document flows were found.

## Installation

Install from a Frappe bench:

```bash
cd /path/to/frappe-bench
bench get-app surveyor_ms <repository-url>
bench --site your-site.local install-app surveyor_ms
bench --site your-site.local migrate
```

For local development from an already cloned repository:

```bash
cd /path/to/frappe-bench
bench get-app surveyor_ms /path/to/surveyor_ms
bench --site your-site.local install-app surveyor_ms
```

## Configuration

After installation:

1. Open the Frappe desk.
2. Go to the `Surveyor Management System` workspace.
3. Create insurer records in `Insurer Master`.
4. Create surveyor records in `Surveyor Profile`.
5. Configure surveyor specializations and insurer empanelments.
6. Confirm SLA, fee, status, permission, and reporting rules with the operations team.

## Usage

Use the workspace shortcuts for daily operations:

| Shortcut | Purpose |
|---|---|
| Survey Assignments | Create and track claim survey assignments. |
| Survey Reports | Prepare preliminary, final, re-survey, or supplementary report records. |
| Site Inspections | Record site inspection details, witnesses, photos, and pending items. |
| Fee Notes | Prepare and track assignment fee notes. |
| Insurer Master | Maintain insurer records. |

## Modules and DocTypes

| Module | DocType | Type | Purpose |
|---|---|---|---|
| SurveyorMS | Insurer Master | Master | Insurer contact, SLA, billing, fee settings, and ERPNext customer reference. |
| SurveyorMS | Surveyor Profile | Master | Surveyor contact, registration, specializations, empanelments, and ERPNext references. |
| SurveyorMS | Survey Assignment | Transaction | Core claim assignment record and operational hub. |
| SurveyorMS | Site Inspection Log | Transaction | Inspection visit log with location, witnesses, photos, and pending items. |
| SurveyorMS | Survey Report | Transaction | Report record with assignment context, recommendation, and financial summary. |
| SurveyorMS | Appointment Letter | Transaction | Appointment letter details, proposed visit, letter body, and email status. |
| SurveyorMS | Follow-up Log | Submittable Transaction | Follow-up record for document requests, visits, insurer queries, payment follow-up, and other actions. |
| SurveyorMS | Repudiation Register | Transaction | Dispute, repudiation, escalation, and resolution tracking. |
| SurveyorMS | Fee Note | Transaction | Fee calculation, line items, totals, invoice reference, and payment tracking. |
| SurveyorMS | Claim Loss Item | Child Table | Claimed and assessed loss item details. |
| SurveyorMS | Required Document Checklist | Child Table | Required, received, attachment, and remarks tracking. |
| SurveyorMS | Inspection Witness | Child Table | Witness or person present during inspection. |
| SurveyorMS | Inspection Photo | Child Table | Inspection photo attachment and remarks. |
| SurveyorMS | Surveyor Specialisation | Child Table | Surveyor specialization categories. |
| SurveyorMS | Surveyor Empanelment | Child Table | Insurer-specific surveyor empanelment details. |
| SurveyorMS | Fee Note Item | Child Table | Fee note line item details. |

## ERPNext Integration Details

| Area | Status |
|---|---|
| Required ERPNext app dependency | Not present. |
| ERPNext imports | Not present. |
| ERPNext DocType Link fields | Not present for Customer, Employee, Supplier, Sales Invoice, or Project; current fields are `Data`. |
| Automatic Sales Invoice creation | Not implemented. |
| Custom fields on ERPNext DocTypes | Not present. |
| Document event hooks for ERPNext | Not present. |

## Custom Fields and Fixtures

No fixtures directory or custom field fixture files were found. The app currently defines its own DocTypes and workspace.

## Permissions

Most parent DocTypes currently grant create, read, write, and delete access to `System Manager`. Child tables inherit access through their parent records.

Production implementations should define business roles such as operations user, surveyor, reviewer, accounts user, and manager if access needs to be separated.

## Reports and Dashboards

No query reports, script reports, dashboards, charts, or number cards were found in the repository. The workspace includes navigation cards and shortcuts, but analytical reporting should be added separately.

## APIs

No whitelisted API methods were found.

## Hooks and Events

| Hook Area | Current Status |
|---|---|
| App metadata | `app_name`, `app_title`, publisher, description, email, license, logo, and home route are defined in `hooks.py`. |
| Apps screen | `add_to_apps_screen` adds the Surveyor Management System app tile. |
| Install hook | `after_app_install` calls `frappe.utils.install.auto_generate_icons_and_sidebar`. |
| Uninstall hook | `after_app_uninstall` calls `frappe.utils.install.delete_desktop_icon_and_sidebar`. |
| Doc events | No active document event hooks. |
| Scheduled tasks | No active scheduler events. |
| Included JS/CSS | No active global JS or CSS includes. |

## Background Jobs

No background jobs or scheduler events are currently enabled.

## Developer Setup

Install development tooling:

```bash
cd apps/surveyor_ms
pre-commit install
```

Run tests from a bench site:

```bash
bench --site your-site.local set-config allow_tests true
bench --site your-site.local run-tests --app surveyor_ms
```

Run formatting and linting:

```bash
pre-commit run --all-files
```

The repository uses:

- Ruff for Python linting and formatting.
- ESLint for JavaScript.
- Prettier for JavaScript, Vue, and SCSS formatting.
- Frappe Semgrep rules and `pip-audit` in CI.

## Project Structure

```text
surveyor_ms/
  hooks.py
  modules.txt
  patches.txt
  public/images/surveyor-management-system.svg
  surveyorms/
    doctype/
      appointment_letter/
      claim_loss_item/
      fee_note/
      fee_note_item/
      follow_up_log/
      inspection_photo/
      inspection_witness/
      insurer_master/
      repudiation_register/
      required_document_checklist/
      site_inspection_log/
      survey_assignment/
      survey_report/
      surveyor_empanelment/
      surveyor_profile/
      surveyor_specialisation/
    workspace/surveyor_management_system/
```

## Migration Notes

`patches.txt` contains no active migration patches. New field changes, data migrations, or operational backfills should be added as Frappe patches when needed.

## Upgrade Guide

1. Pull the latest app code.
2. Review release notes or migration patches.
3. Back up the site.
4. Run:

```bash
bench --site your-site.local migrate
bench --site your-site.local clear-cache
```

5. Verify the Surveyor Management System workspace and core DocTypes.

## Uninstallation

Use standard bench uninstallation:

```bash
bench --site your-site.local uninstall-app surveyor_ms
```

Back up the site before uninstalling. Removing an app can remove or orphan records depending on site configuration and Frappe behavior.

## Troubleshooting

| Issue | Check |
|---|---|
| App tile does not appear | Run migrate, clear cache, and confirm `add_to_apps_screen` hook is loaded. |
| Workspace is missing | Confirm the workspace JSON exists and run `bench --site your-site.local migrate`. |
| Link fields fail validation | Confirm linked master records such as insurer and surveyor records exist. |
| Tests do not run | Confirm `allow_tests` is enabled on the site. |
| ERPNext records are not created | This repository does not currently implement automatic ERPNext document creation. |

## Security

- Review and harden permissions before production use.
- Avoid giving all operational users `System Manager`.
- Confirm attachment permissions for inspection photos, signatures, report PDFs, and claim documents.
- Add validation for sensitive operational rules where required.
- Review personal data fields such as email, phone, signatures, insured contact information, and attachments.

## Repository Evidence Reviewed

| File / Area | Evidence Found |
|---|---|
| `pyproject.toml` | App name `surveyor_ms`, description, Python `>=3.14`, flit build backend, ruff config. |
| `surveyor_ms/__init__.py` | App version `0.0.1`. |
| `surveyor_ms/hooks.py` | App metadata, app tile, logo, home route, install and uninstall hooks. No active doc events or scheduler events. |
| `surveyor_ms/modules.txt` | Defines module `SurveyorMS`. |
| `surveyor_ms/patches.txt` | No active migration patches. |
| `surveyor_ms/surveyorms/doctype/*/*.json` | Defines the app DocTypes, fields, child tables, naming, permissions, field dependencies, fetches, and tracking. |
| `surveyor_ms/surveyorms/doctype/*/*.py` | Controllers inherit from `frappe.model.document.Document` and are currently minimal. |
| `surveyor_ms/surveyorms/doctype/follow_up_log/follow_up_log.js` | Minimal client script placeholder. |
| `surveyor_ms/surveyorms/workspace/surveyor_management_system/surveyor_management_system.json` | Defines the public workspace, shortcuts, and navigation cards. |
| `.github/workflows/ci.yml` | CI installs the app on a Frappe bench and runs tests using Python 3.14, Node 24, MariaDB, and Redis. |
| `.github/workflows/linter.yml` | Runs pre-commit, Frappe Semgrep rules, and `pip-audit`. |
| `.pre-commit-config.yaml` | Configures ruff, eslint, prettier, and common pre-commit checks. |
| `license.txt` | MIT license text, but copyright placeholders remain. |

## To Confirm Before Publishing

- Exact supported Frappe version.
- Whether Python 3.14 is intentional for all target deployments.
- Whether ERPNext should remain optional or become a required dependency.
- Whether ERPNext customer, employee, supplier, project, and sales invoice references should become Link fields or automated integrations.
- Production role and permission model.
- Required reports, dashboards, charts, and management KPIs.
- Whether custom validations should be added to controllers.
- Screenshots and demo data.
- Correct license copyright year and holder.
- Public repository URL and preferred branch name.
- Maintainer and support contact details.

## Support and Maintenance

Maintainer information from repository metadata:

| Field | Value |
|---|---|
| Publisher | Emanuel Fidelis |
| Email | emanuelkagombora28@gmail.com |

## Contributing

1. Create a branch for your change.
2. Install pre-commit hooks.
3. Keep DocType JSON, Python controllers, and workspace metadata consistent.
4. Run formatting, linting, and tests before opening a pull request.

```bash
pre-commit run --all-files
bench --site your-site.local run-tests --app surveyor_ms
```

## Versioning

Current app version: `0.0.1`

Use semantic versioning or a documented release scheme before production rollout.

## License

MIT. See `license.txt`.

Note: the license file currently contains placeholder copyright text and should be updated before publishing.

## Maintainers

| Name | Contact |
|---|---|
| Emanuel Fidelis | emanuelkagombora28@gmail.com |
