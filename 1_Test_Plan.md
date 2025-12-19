# Agile QA Test Plan


## 1. Purpose

This test plan describes the QA approach for testing an e-commerce web application. 
The goal is to ensure core functionality, usability, accessibility, API, and data integrity meet the defined requirements before release.

## 2. Scope of Testing

2.1 In Scope

Manual functional testing
Accessibility testing (WCAG 2.1 AA)
Cross-browser testing (Chrome, Safari)
API testing (REST)
Database / SQL validation
Smoke, Sanity, and Regression Testing

2.2 Out of Scope

Performance and load testing
Security and penetration testing

## 3. Test Strategy

3.1 Agile Testing Approach

Testing performed within each sprint
Test cases created from user stories and acceptance criteria
Defects logged and re-tested during the same sprint when possible

## 4. Types of Testing

4.1 Functional Manual Testing

UI and business logic validation
Positive and negative scenarios
Form validations and error handling

4.2 Accessibility (a11y) Testing

WCAG 2.1 AA checks
Keyboard navigation
Screen reader support
Color contrast and focus indicators

4.3 Cross-Browser / Platform Testing

Browsers: Chrome, Safari
Platforms: Windows, macOS

4.4 API Testing

REST API request/response validation
HTTP status codes
Error handling and authorization

4.5 Database / SQL Testing

CRUD operations validation
Data consistency between UI, API, and database

## 5. Test Environment

QA/Staging environment
Production-like configuration
Test data prepared in advance

## 6. Test Tools

Test management: TestRail
Defect tracking: Jira
API testing: Postman
Database testing: SQL (MySQL)
Accessibility: VoiceOver, browser DevTools
Cross-browser testing: Sauce Labs

## 7. Test Deliverables

Test plan
Test cases and scenarios
Accessibility checklist
API and SQL test cases
Defect reports

## 8. Entry & Exit Criteria

Entry Criteria
Requirements and acceptance criteria defined
QA environment available
Exit Criteria
All planned test cases executed
No open Critical or High severity defects
Accessibility and cross-browser checks completed

## 9. Defect Management

Defects logged in Jira
Severity levels: Critical, High, Medium, Low
Defects are re-tested after fixes

## 10. Test Schedule (Per Sprint)

Test planning and design
Test execution
Regression testing
Test summary

## 11. Roles & Responsibilities

QA Engineer: Test design, execution, defect reporting
Developers: Defect fixes
Product Owner: Requirements validation

## 12. Risks & Mitigation

Requirement changes → early QA involvement
Environment issues → communication and buffer time
Limited test data → early preparation

## 13. Assumptions

Requirements are clear and stable
API and database access available
Supported browsers are predefined

## 14. Approval

Prepared by: QA Engineer
Reviewed by: Portfolio Reviewer


