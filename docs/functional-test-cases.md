# BRD-Derived Functional Test Cases
 
**Document Version:** 1.0 
**Date Prepared:** 2025-11-13 
**Prepared By:** QA Team 
**Source Documents:** Mexico_Onboarding_BRD.md, Mexico_Onboarding_Functional_Specs.md, Epics.md, Features.md, Epic_to_Requirements_Mapping.md
 
---
 
## Document Control
 
| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-11-13 | QA Team | Initial creation of BRD-derived test cases |
 
---
 
## Table of Contents
 
1. [Introduction](#1-introduction)
2. [Test Case Organization](#2-test-case-organization)
3. [Business Objective Validation Tests](#3-business-objective-validation-tests)
4. [Business Process Tests](#4-business-process-tests)
5. [Functional Requirements Tests](#5-functional-requirements-tests)
6. [Integration & Dependency Tests](#6-integration--dependency-tests)
7. [Compliance & Regulatory Tests](#7-compliance--regulatory-tests)
8. [Risk Mitigation Tests](#8-risk-mitigation-tests)
9. [Non-Functional Requirements Tests](#9-non-functional-requirements-tests)
10. [Acceptance Criteria Tests](#10-acceptance-criteria-tests)
 
---
 
## 1. Introduction
 
### 1.1 Purpose
 
This document contains comprehensive functional test cases derived directly from the Business Requirements Document (BRD) for the Mexico Global Onboarding (ONB) system. Each test case is designed to validate specific business objectives, requirements, processes, and acceptance criteria documented in the BRD.
 
### 1.2 Scope
 
These test cases cover:
- All 8 primary business objectives (BRD Section 1.3.1)
- All 15 high-level requirements (HLR-001 to HLR-015)
- All 111 functional requirements (FR-001 to FR-111)
- All 30 non-functional requirements (NFR-001 to NFR-030)
- All 26 business rules (BR1 to BR26)
- 10 identified risks requiring validation
- Key assumptions and constraints requiring verification
 
### 1.3 Test Case Numbering Convention
 
Test cases are numbered using the format: **TC-BRD-NNNN**
 
Where:
- **TC** = Test Case
- **BRD** = Derived from Business Requirements Document
- **NNNN** = Sequential 4-digit number (0001-9999)
 
### 1.4 Traceability
 
All test cases maintain bidirectional traceability to:
- BRD section references (HLR-XXX, FR-XXX, NFR-XXX, BR-XX)
- Epic and Feature IDs (EP-XXX, FE-XXX)
- Requirements Traceability Matrix entries (RTM-XXX)
- User Stories (US-XXX where applicable)
 
---
 
## 2. Test Case Organization
 
### 2.1 Test Categories
 
Test cases are organized into the following categories:
 
| Category | Test ID Range | Description |
|----------|---------------|-------------|
| Business Objective Validation | TC-BRD-0001 to TC-BRD-0100 | Validates achievement of business objectives |
| Business Process Tests | TC-BRD-0101 to TC-BRD-0200 | Validates end-to-end business processes |
| Functional Requirements | TC-BRD-0201 to TC-BRD-0600 | Validates functional requirements (FR-001 to FR-111) |
| Integration Tests | TC-BRD-0601 to TC-BRD-0700 | Validates external system integrations |
| Compliance Tests | TC-BRD-0701 to TC-BRD-0800 | Validates regulatory and compliance requirements |
| Risk Mitigation Tests | TC-BRD-0801 to TC-BRD-0850 | Validates risk mitigation strategies |
| Non-Functional Tests | TC-BRD-0851 to TC-BRD-0950 | Validates NFRs (performance, security, usability) |
| Acceptance Criteria | TC-BRD-0951 to TC-BRD-1000 | Validates specific acceptance criteria |
 
### 2.2 Priority Levels
 
| Priority | Description | Example |
|----------|-------------|---------|
| Critical | Must pass for system go-live; core business functionality | Offer data ingestion, candidate registration |
| High | Important functionality; significant impact if failed | Form validation, email notifications |
| Medium | Standard functionality; moderate impact | Report generation, UI enhancements |
| Low | Nice-to-have features; minimal impact | Optional fields, tooltips |
 
---
 
## 3. Business Objective Validation Tests
 
### TC-BRD-0001: Validate Automated Offer Processing from C-Hire
 
**Traceability:**
- BRD Reference: BRD-OBJ-01 (Automate Offer Processing), HLR-001, FR-012 to FR-021
- FRS Reference: Section 3.3.1 (Offer Data Ingestion)
- Epic/Feature: EP-001 / FE-001, FE-002, FE-003
- RTM Entry: RTM-FR-012 to RTM-FR-021
 
**Objective:**
Verify that the system automatically ingests offer data from C-Hire every hour and triggers appropriate onboarding workflows without manual intervention.
 
**Test Type:** End-to-End / Integration 
**Priority:** Critical 
**Execution Approach:** Automated with manual validation
 
**Preconditions:**
- C-Hire system is configured to export offer CSV files to Azure Blob Storage hourly
- Azure Function is deployed and configured with blob trigger
- ONB database is accessible and schema is up-to-date
- Test offers exist in C-Hire with "Offer Accepted" status
- Email service is configured for welcome mailer delivery
 
**Test Data Requirements:**
- **Offer CSV File**: Containing 10 test offers covering all 10 eligible hire types
- **Candidate Data**: Valid personal emails, candidate IDs, offer IDs, requisition IDs
- **Hire Types**: Permanent, FTC, Contractor to Employee Conversion, Re-hire, Rebadging, etc.
- **Data Classification**: Synthetic test data (no real PII)
- **Data Source**: Test data generator script
- **Refresh Cadence**: Daily
 
**Test Steps:**
 
| Step # | Action | Expected Result | Notes |
|--------|--------|-----------------|-------|
| 1 | Prepare test CSV file with 10 offers (various hire types, all "Offer Accepted" status) | CSV file ready with valid structure | Include all required fields per C-Hire schema |
| 2 | Upload CSV file to Azure Blob Storage in designated container | File uploaded successfully | Monitor blob storage logs |
| 3 | Verify Azure Function is triggered automatically | Function execution logged within 5 minutes | Check Application Insights |
| 4 | Verify offer data is parsed and validated | All 10 offers pass validation; logged as successful | Check validation logs |
| 5 | Verify offers are stored in ONB database | 10 new records in Candidates table with correct status | Query database |
| 6 | Verify welcome mailer is triggered for each candidate | 10 welcome emails queued for delivery | Check email service logs |
| 7 | Verify registration links are generated | Each email contains unique, valid registration link with 30-day expiry | Inspect email content |
| 8 | Verify audit trail is created | All offer ingestion activities logged with timestamp and file details | Query AuditLogs table |
| 9 | Test with invalid CSV (missing required fields) | Processing fails gracefully; errors logged; no partial data stored | Error handling validation |
| 10 | Test with duplicate offers (re-upload same file) | Duplicates detected and skipped; logged appropriately | Idempotency check |
 
**Expected Outcome:**
- 100% of valid offers automatically processed within 1 hour of file upload
- Welcome mailers sent within 5 minutes of successful processing
- Zero manual intervention required
- Complete audit trail maintained
- Invalid data handled gracefully with appropriate error logging
 
**Actual Result:** [To be completed during execution] 
**Status:** Not Executed 
**Executed By:** [Tester Name] 
**Execution Date:** [YYYY-MM-DD] 
**Defect IDs:** [DEF-XXXX if applicable]
 
**Post-Conditions:**
- Test offers remain in database for subsequent test scenarios
- Cleanup script available to reset test data
- Audit logs archived for analysis
 
**Risk Coverage:**
- Mitigates R1: Data quality issues in C-Hire leading to incorrect offer processing
- Addresses A5: C-Hire is single source of truth for offer data
 
**Compliance Mapping:**
- Audit trail requirements per ISO 27001
- Data processing transparency per GDPR Article 30
 
**Notes & Edge Cases:**
- **Boundary Condition**: Large CSV file (1000+ offers) - test processing time remains < 5 minutes
- **Error Scenario**: Blob storage unavailable - retry mechanism activates
- **Alternative Flow**: CSV with mixed valid/invalid records - valid records processed, invalid logged
- **Known Limitation**: 1-hour maximum delay in processing due to hourly refresh cycle
 
---
 
### TC-BRD-0002: Validate Secure Access Provisioning via EUMS Integration
 
**Traceability:**
- BRD Reference: BRD-OBJ-02 (Secure Access Provisioning), HLR-002, FR-085 to FR-091
- FRS Reference: Section 3.3.2 (Access Provisioning)
- Epic/Feature: EP-002 / FE-009, FE-010, FE-016
- RTM Entry: RTM-FR-085 to RTM-FR-091
 
**Objective:**
Verify that the system integrates with Microsoft Azure via EUMS to automatically provision secure access to the OneCognizant external platform for new candidates.
 
**Test Type:** Integration 
**Priority:** Critical 
**Execution Approach:** Automated with manual verification
 
**Preconditions:**
- EUMS integration endpoint is accessible and authenticated
- OAuth 2.0 client credentials configured in Azure Key Vault
- Test candidate record exists in ONB database with "Offer Accepted" status
- OneCognizant external platform is operational
 
**Test Data Requirements:**
- **Candidate Record**: Valid personal email, first name, last name, candidate ID
- **EUMS Credentials**: OAuth 2.0 client ID and secret
- **Test Accounts**: 5 candidates with unique email addresses
- **Data Source**: Test database seed script
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Trigger access provisioning for test candidate | ONB system initiates OAuth 2.0 authentication with EUMS |
| 2 | Verify OAuth token acquisition | Valid access token obtained and cached |
| 3 | Verify user account creation request sent to EUMS | API call includes candidate email, name, and required metadata |
| 4 | Verify EUMS processes request successfully | HTTP 201 Created response received with user ID |
| 5 | Verify user account details stored in ONB | Candidate record updated with external user ID |
| 6 | Test access revocation (offer cancelled) | Revocation request sent to EUMS; account disabled; logged |
 
**Expected Outcome:**
- Access provisioned within 5 minutes of offer acceptance
- 100% success rate for valid provisioning requests
- Retry mechanism handles transient failures
- Complete audit trail maintained
 
**Risk Coverage:**
- Mitigates R2: Azure/EUMS integration failure
- Addresses D2: Dependency on EUMS availability
 
---
 
### TC-BRD-0003: Validate Multi-Language Support (Spanish)
 
**Traceability:**
- BRD Reference: BRD-OBJ-05 (Support Multi-Language), HLR-007, FR-101 to FR-105
- Epic/Feature: EP-005 / FE-039 to FE-047
- RTM Entry: RTM-FR-101 to RTM-FR-105
 
**Objective:**
Verify complete Spanish language support across UI, emails, and forms with proper translations and cultural adaptations.
 
**Test Type:** Functional / Localization 
**Priority:** High 
**Execution Approach:** Manual with automated regression
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Access portal and select "Español" | All UI elements switch to Spanish |
| 2 | Verify landing page content | Welcome message, instructions in Spanish with proper grammar |
| 3 | Register new account | Registration form labels in Spanish; validation messages translated |
| 4 | Verify welcome email | Email subject and body in Spanish |
| 5 | Complete all 9 forms | Form content, labels, help text all in Spanish |
| 6 | Test validation messages | All errors displayed in Spanish |
| 7 | Switch language to English mid-session | Language changes immediately; form data preserved |
 
**Expected Outcome:**
- 100% UI elements have accurate Spanish translations
- Professional translation quality verified by native speaker
- Cultural adaptations applied (date formats, address fields)
 
**Risk Coverage:**
- Mitigates R6: Language translation quality
- Addresses BR15: Language support requirement
 
---
 
### TC-BRD-0004: Validate Mexico-Specific Field Requirements
 
**Traceability:**
- BRD Reference: BRD-OBJ-06 (Regional Adaptation), HLR-011, BR24, FR-051 to FR-054
- Epic/Feature: EP-003 / FE-024
- RTM Entry: RTM-FR-051 to RTM-FR-054
 
**Objective:**
Verify Mexico-specific mandatory fields (CURP, RFC, INFONAVIT, FONACOT) are properly validated and synced to HCM.
 
**Test Type:** Functional / Compliance 
**Priority:** Critical 
**Execution Approach:** Automated
 
**Test Data Requirements:**
- **Valid CURP**: 18 characters, proper format
- **Valid RFC**: 13 characters with homoclave
- **INFONAVIT**: Optional, numeric 10-11 digits
- **FONACOT**: Optional, alphanumeric 9-16 characters
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Open Personal Details Form | Mexico fields displayed: CURP, RFC (mandatory), INFONAVIT, FONACOT (optional) |
| 2 | Leave CURP empty and submit | Validation error: "CURP es un campo obligatorio" |
| 3 | Enter CURP with 17 characters | Validation error: "CURP debe tener exactamente 18 caracteres" |
| 4 | Enter valid CURP | Field accepts input; no error |
| 5 | Enter valid RFC (13 chars with homoclave) | Field accepts input |
| 6 | Submit form with all valid fields | Form submitted successfully |
| 7 | Verify data sync to HCM | Mexico fields synced correctly |
 
**Expected Outcome:**
- CURP and RFC enforced as mandatory
- Strict format validation prevents invalid data
- Fields synced to HCM for compliance
 
**Compliance Mapping:**
- CURP validation per RENAPO standards
- RFC validation per SAT requirements
 
---
 
## 4. Business Process Tests
 
### TC-BRD-0101: End-to-End Offer-to-Onboarding Process
 
**Traceability:**
- BRD Reference: Section 4.2 (Proposed Solution), All HLRs
- Epic/Feature: EP-001 to EP-007
- RTM Entry: RTM-PROC-001
 
**Objective:**
Validate complete onboarding process from offer acceptance through Day 1 transition.
 
**Test Type:** End-to-End 
**Priority:** Critical 
**Execution Approach:** Manual with automated checkpoints
 
**Test Steps:**
 
| Step # | Action | Expected Result | Duration |
|--------|--------|-----------------|----------|
| 1 | Recruiter updates offer to "Accepted" in C-Hire | Offer status updated | Baseline |
| 2 | ONB ingests offer data (hourly) | Candidate record created | < 1 hour |
| 3 | EUMS provisioning triggered | External user account created | < 5 min |
| 4 | Welcome email sent | Email delivered with registration link | < 5 min |
| 5 | Candidate registers and logs in | Account created; dashboard loads | < 2 min |
| 6 | Candidate completes all 9 forms | Forms submitted with e-signatures | Variable |
| 7 | Forms pushed to E-Storage | All 9 forms archived | Immediate |
| 8 | Core HR creates Employee ID | ID assigned in HCM | Day -10 to -1 |
| 9 | One-time sync to HCM on Day 1 | All data synced | < 10 min |
| 10 | Transition to post-joining module | Post-joining tasks displayed | Day 0 |
 
**Expected Outcome:**
- Complete flow without manual intervention
- Time-to-onboard reduced from 3-5 days to < 1 hour
- No data loss throughout process
- Complete audit trail maintained
 
---
 
## 5. Functional Requirements Tests
 
### TC-BRD-0201: Validate Eligible Hire Types Processing
 
**Traceability:**
- BRD Reference: FR-001 to FR-011, HLR-013
- Epic/Feature: EP-001 / FE-004
- RTM Entry: RTM-FR-001 to RTM-FR-011
 
**Objective:**
Verify system processes all 10 eligible hire types and rejects ineligible types.
 
**Test Type:** Functional 
**Priority:** Critical 
**Execution Approach:** Automated
 
**Test Data Requirements:**
- **Eligible Hire Types**: Permanent, FTC, Contractor to Employee Conversion, Contractor to Fixed Term Conversion, Employee to Fixed Term Conversion, Fixed Term Extension, Fixed Term to Employee Conversion, Re-hire, Rebadging, Rehire-Fixed Term Employee
- **Ineligible Type**: Test with "Intern" or other non-eligible type
 
**Test Steps:**
 
| Step # | Hire Type | Expected Result |
|--------|-----------|-----------------|
| 1 | Permanent | Processed successfully |
| 2 | FTC (Fixed Term Contract) | Processed successfully |
| 3 | Contractor to Employee Conversion | Processed successfully |
| 4 | Contractor to Fixed Term Conversion | Processed successfully |
| 5 | Employee to Fixed Term Conversion | Processed successfully |
| 6 | Fixed Term Extension | Processed successfully |
| 7 | Fixed Term to Employee Conversion | Processed successfully |
| 8 | Re-hire | Processed successfully |
| 9 | Rebadging | Processed successfully |
| 10 | Rehire-Fixed Term Employee | Processed successfully |
| 11 | Intern (ineligible) | Rejected with error message |
 
**Expected Outcome:**
- All 10 eligible hire types processed
- Ineligible types rejected with clear error message
- Rejection logged in audit trail
 
---
 
### TC-BRD-0202: Validate Welcome Mailer Generation
 
**Traceability:**
- BRD Reference: FR-022 to FR-027, HLR-003
- Epic/Feature: EP-001 / FE-005
- RTM Entry: RTM-FR-022 to RTM-FR-027
 
**Objective:**
Verify welcome mailer is sent with correct content, registration link, and bilingual instructions.
 
**Test Type:** Functional 
**Priority:** Critical 
**Execution Approach:** Automated
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Trigger welcome mailer for new candidate | Email queued for delivery |
| 2 | Verify email sent to personal email address | Email delivered to correct recipient |
| 3 | Verify bilingual content (English and Spanish) | Both languages included in email body |
| 4 | Verify registration link included | Unique link present with 30-day expiry |
| 5 | Verify login instructions | Clear steps for registration and login |
| 6 | Test registration link validity | Link works and loads registration page |
| 7 | Test link expiry (31 days later) | Link expired; error message displayed |
| 8 | Track email delivery status | Delivery status logged (sent/failed) |
 
**Expected Outcome:**
- Welcome mailer sent within 5 minutes of trigger
- Bilingual content accurate and professional
- Registration link valid for 30 days
- Delivery tracking complete
 
---
 
### TC-BRD-0203: Validate Pre-Joining Forms Sequence and Status
 
**Traceability:**
- BRD Reference: FR-030 to FR-040, BR5, BR12, BR13
- Epic/Feature: EP-003 / FE-019, FE-027
- RTM Entry: RTM-FR-030 to RTM-FR-040
 
**Objective:**
Verify all 9 pre-joining forms displayed in correct sequence with accurate status tracking.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Manual
 
**Test Data Requirements:**
- **Forms**: Global Associate Privacy Notice, Statement of Company Policy, Company Property Attestation, Equipment Request, Personal Details, Confidential Info Agreement, New Hire Template, Beneficiarios, INFONAVIT
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Log in to candidate dashboard | Task list displays 9 forms |
| 2 | Verify form sequence | Forms in correct order per FR-036 |
| 3 | Verify initial status | All forms show "Yet to start" |
| 4 | Verify estimated time displayed | Time shown for applicable forms (5, 5, 15, 10 minutes) |
| 5 | Open form and partially complete | Status changes to "Pending" |
| 6 | Complete and submit form | Status changes to "Completed" |
| 7 | Verify task actions | "Start Now" for new; "Modify" for completed |
| 8 | Verify e-signature on all forms | Standard declaration present |
| 9 | Verify immediate E-Storage push | Form pushed within 30 seconds |
 
**Expected Outcome:**
- All 9 forms present in correct sequence
- Status transitions accurate ("Yet to start" → "Pending" → "Completed")
- Task actions appropriate based on status
- E-signature captured on all forms
 
---
 
### TC-BRD-0204: Validate Personal Details Form Auto-Population
 
**Traceability:**
- BRD Reference: FR-041 to FR-062, BR14
- Epic/Feature: EP-003 / FE-021
- RTM Entry: RTM-FR-041 to RTM-FR-062
 
**Objective:**
Verify Personal Details Form fields are auto-populated from C-Hire data and non-editable where appropriate.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Automated
 
**Test Data Requirements:**
- **C-Hire Data**: Candidate ID, Name, Personal Email, DOJ, Department, Work Location, Job Code, Manager ID
 
**Test Steps:**
 
| Step # | Field | Expected Behavior |
|--------|-------|-------------------|
| 1 | CHIRE Candidate ID | Auto-populated, non-editable |
| 2 | Date of Hire | Auto-populated from offer, non-editable |
| 3 | First Name | Auto-populated from C-Hire, non-editable |
| 4 | Middle Name | Auto-populated from C-Hire, non-editable |
| 5 | Full Last Name | Auto-populated from C-Hire, non-editable |
| 6 | Personal Email | Auto-populated from offer, non-editable |
| 7 | Department | Auto-populated from offer, non-editable |
| 8 | Work Location | Auto-populated from offer, non-editable |
| 9 | Job Code | Auto-populated from offer, non-editable |
| 10 | Manager ID | Auto-populated from C-Hire, non-editable |
| 11 | Date of Birth | Editable, validation for age ≥ 18 |
| 12 | CURP, RFC | Editable, mandatory with validation |
 
**Expected Outcome:**
- All specified fields auto-populated from C-Hire
- Auto-populated fields are non-editable
- Manual entry fields editable with validation
- Data accuracy maintained from source system
 
---
 
### TC-BRD-0205: Validate Beneficiarios Form Constraints
 
**Traceability:**
- BRD Reference: FR-064 to FR-068, BR7
- Epic/Feature: EP-003 / FE-025
- RTM Entry: RTM-FR-064 to RTM-FR-068
 
**Objective:**
Verify Beneficiarios Form enforces minimum 1 and maximum 4 beneficiaries with percentage validation.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Manual
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Open Beneficiarios Form | Form allows adding beneficiaries |
| 2 | Attempt to submit with 0 beneficiaries | Validation error: "Minimum 1 beneficiary required" |
| 3 | Add 1 beneficiary with 100% | Form submits successfully |
| 4 | Add 2 beneficiaries (50%, 50%) | Form submits successfully |
| 5 | Add 3 beneficiaries (40%, 35%, 25%) | Form submits successfully |
| 6 | Add 4 beneficiaries (25% each) | Form submits successfully |
| 7 | Attempt to add 5th beneficiary | Add button disabled after 4 beneficiaries |
| 8 | Add 3 beneficiaries (40%, 40%, 10%) | Validation error: "Percentages must total 100%" |
| 9 | Verify relationship field is free text | No dropdown; accepts any text |
| 10 | Verify no field validations per FR-068 | Free text entry for all fields |
 
**Expected Outcome:**
- Minimum 1 beneficiary enforced
- Maximum 4 beneficiaries enforced
- Percentage total must equal 100%
- Relationship field accepts free text
 
---
 
### TC-BRD-0206: Validate Task Reminder Notifications
 
**Traceability:**
- BRD Reference: FR-071 to FR-075, BR21
- Epic/Feature: EP-003 / FE-064
- RTM Entry: RTM-FR-071 to RTM-FR-075
 
**Objective:**
Verify email reminders sent at Day -5, Day -3, and Day -1 for incomplete pre-joining tasks.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Automated with time simulation
 
**Test Data Requirements:**
- **Test Candidate**: DOJ in 6 days, 50% forms complete
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Set candidate DOJ to 6 days from today | Candidate created with future DOJ |
| 2 | Complete 4 of 9 forms (50% complete) | Status shows incomplete |
| 3 | Run reminder job for Day -5 | Reminder email sent; logged |
| 4 | Verify email content | Lists incomplete forms; encourages completion |
| 5 | Fast-forward to Day -3 (simulate) | Second reminder email sent |
| 6 | Verify escalation in tone | Email more urgent than Day -5 |
| 7 | Fast-forward to Day -1 | Final reminder email sent |
| 8 | Verify final reminder urgency | Critical tone; lists incomplete forms |
| 9 | Complete all forms | No further reminders sent |
| 10 | Verify push notifications on UI | Notifications displayed in portal |
 
**Expected Outcome:**
- Reminders sent at Day -5, -3, -1 if incomplete
- Email content appropriate for urgency level
- Reminders stop once 100% complete
- Push notifications also displayed
 
---
 
### TC-BRD-0207: Validate HRSS Country-Level Access
 
**Traceability:**
- BRD Reference: FR-076, BR10
- Epic/Feature: EP-006 / FE-048
- RTM Entry: RTM-FR-076
 
**Objective:**
Verify HRSS users have access to all candidates in their assigned country (Mexico).
 
**Test Type:** Functional / Access Control 
**Priority:** Critical 
**Execution Approach:** Manual
 
**Test Data Requirements:**
- **HRSS User**: User with Mexico country assignment
- **Candidates**: 20 Mexico candidates, 5 US candidates (for access boundary test)
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Log in as HRSS user (Mexico assignment) | HRSS dashboard loads |
| 2 | Verify candidate list | All 20 Mexico candidates displayed |
| 3 | Verify US candidates not visible | US candidates not in list |
| 4 | Attempt to access US candidate by direct URL | Access denied; error message |
| 5 | Search for Mexico candidate | Search returns results |
| 6 | Filter candidates by status | Filter works correctly |
| 7 | Click on any Mexico candidate | Candidate details accessible |
| 8 | Verify audit log | Access logged with HRSS user ID |
 
**Expected Outcome:**
- HRSS sees all candidates in assigned country
- Cannot access candidates from other countries
- Access control enforced at data and UI levels
- All access attempts logged
 
---
 
### TC-BRD-0208: Validate RC Candidate-Specific Access
 
**Traceability:**
- BRD Reference: FR-077, BR11
- Epic/Feature: EP-006 / FE-049
- RTM Entry: RTM-FR-077
 
**Objective:**
Verify RC users can only access candidates tagged to them in C-Hire.
 
**Test Type:** Functional / Access Control 
**Priority:** Critical 
**Execution Approach:** Manual
 
**Test Data Requirements:**
- **RC User**: User assigned to 5 specific candidates
- **Candidates**: 5 assigned candidates, 15 unassigned candidates
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Log in as RC user | RC dashboard loads |
| 2 | Verify candidate list | Only 5 assigned candidates displayed |
| 3 | Verify unassigned candidates not visible | Other candidates not in list |
| 4 | Attempt to access unassigned candidate by URL | Access denied; error message |
| 5 | Click on assigned candidate | Details accessible |
| 6 | Use resend welcome mailer for assigned candidate | Function works |
| 7 | Attempt to generate report for all candidates | Report includes only assigned candidates |
| 8 | Verify audit log | All access attempts logged |
 
**Expected Outcome:**
- RC sees only assigned candidates
- Cannot access unassigned candidates
- Access control strictly enforced
- Limited reporting scope to assigned candidates
 
---
 
### TC-BRD-0209: Validate Resend Welcome Mailer Function
 
**Traceability:**
- BRD Reference: FR-079
- Epic/Feature: EP-006 / FE-052
- RTM Entry: RTM-FR-079
 
**Objective:**
Verify HRSS and RC can resend welcome mailer to candidates.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Manual
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | HRSS selects candidate from list | Candidate details displayed |
| 2 | Click "Resend Welcome Mailer" button | Confirmation prompt: "Are you sure?" |
| 3 | Confirm resend | Email queued; success notification |
| 4 | Verify email sent to candidate | Email delivered within 5 minutes |
| 5 | Verify new registration link generated | New link created (old link still valid) |
| 6 | Test resending multiple times | Each resend creates new email; all logged |
| 7 | Verify audit trail | All resend actions logged with user ID and timestamp |
 
**Expected Outcome:**
- Resend function available to HRSS and RC
- Confirmation prompt prevents accidental resend
- Email delivered successfully
- All actions audited
 
---
 
### TC-BRD-0210: Validate Report Generation and Export
 
**Traceability:**
- BRD Reference: FR-080 to FR-084, HLR-015
- Epic/Feature: EP-006 / FE-053
- RTM Entry: RTM-FR-080 to RTM-FR-084
 
**Objective:**
Verify HRSS/RC can generate and export reports in CSV and Excel formats.
 
**Test Type:** Functional 
**Priority:** High 
**Execution Approach:** Automated
 
**Test Data Requirements:**
- **Candidates**: 50 candidates with various completion statuses
 
**Test Steps:**
 
| Step # | Action | Expected Result |
|--------|--------|-----------------|
| 1 | Click "Download Report" button | Report options dialog opens |
| 2 | Select CSV format | Option selected |
| 3 | Choose date range (last 30 days) | Date filter applied |
| 4 | Generate report | CSV file downloads |
| 5 | Open CSV file | Data displays correctly |
| 6 | Verify report columns | Name, Candidate ID, Offer ID, Status, % Complete, Task details |
| 7 | Verify data accuracy | All 50 candidates listed with correct data |
| 8 | Repeat with Excel format | Excel file downloads |
| 9 | Verify Excel formatting | Headers bold; data formatted properly |
| 10 | Test with no candidates (empty filter) | Empty report with message |
 
**Expected Outcome:**
- Reports generated in <10 seconds for 100 candidates
- CSV and Excel formats both functional
- Data accuracy 100%
- Empty state handled gracefully
 
---