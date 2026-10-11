# Test Cases — Home Credit LAP Qualification Voice Agent

## 1. Overview

**Project:** Home Credit Loan Against Property (LAP) Qualification Voice Agent  
**Platform:** Retell AI  
**Testing Type:** Conversational, functional, eligibility-rule, and edge-case testing

### Objective

To verify that the voice agent conducts a natural customer conversation, collects the required eligibility information, applies business rules correctly, handles interruptions and corrections, and routes eligible or special-case customers appropriately.

## 2. Test Cases

| Test ID | Scenario | Test Input / Customer Response | Expected Result | Status |
|---|---|---|---|---|
| TC-01 | Successful preliminary qualification | Residential property, joint ownership, original documents available, ₹50 lakh requested, salaried with bank income, ₹1 crore market value, 10-year tenure | Collect all required details and offer handoff to a senior loan expert without promising final approval | Passed |
| TC-02 | Agricultural property | "The property is agricultural land." | Politely disqualify the customer and end the call without continuing eligibility questions | Passed |
| TC-03 | Income received in cash | "I'm self-employed, and I receive all my income in cash." | Disqualify because income must be received through a bank | Update with actual result |
| TC-04 | Original documents unavailable | "I only have photocopies of the property documents." | Disqualify because original documents must be available | Update with actual result |
| TC-05A | Loan amount above the limit — accepts | Customer requests ₹90 lakh and then agrees to proceed with ₹75 lakh | Explain the ₹75 lakh limit and continue eligibility checks after acceptance | Update with actual result |
| TC-05B | Loan amount above the limit — refuses | Customer requests ₹90 lakh and refuses the ₹75 lakh limit | Politely explain the limit and end the qualification call | Update with actual result |
| TC-06 | Existing property loan / loan transfer | "I already have a loan on this property and want to reduce my EMI through a transfer." | Refer the customer to a loan-transfer specialist and end the current qualification call | Update with actual result |
| TC-07 | Busy customer | "I'm busy right now. Could you call me this evening?" | Ask for or confirm a preferred callback time and end the current call without eligibility questions | Update with actual result |
| TC-08 | Eligibility details provided out of order | Customer provides property type, ownership, document availability, loan amount, occupation, income mode, market value, and tenure in one response | Capture all provided details and ask only for genuinely missing information | Completed — verify result |
| TC-09 | Customer corrects an earlier answer | Customer first says residential, then corrects it to agricultural | Update the property type to agricultural, disqualify, and end the call | Pending confirmation |

## 3. Successful Qualification Criteria

A customer can proceed to the senior loan expert handoff only after all seven eligibility categories are collected and the applicable criteria are satisfied:

1. **Property type:** Residential, Commercial, or Industrial.
2. **Ownership:** Sole or Joint.
3. **Original documents:** Must be available.
4. **Loan amount:** Must not exceed ₹75 lakh unless the customer accepts the ₹75 lakh limit after initially requesting more.
5. **Occupation and income mode:** Salaried or Self-employed, with income received through a bank.
6. **Market value:** Estimated current market value must be captured. No minimum value is specified in the assignment.
7. **Tenure:** Between 3 and 15 years, inclusive.

Existing property loans or requests to reduce EMI through a loan transfer must be routed to the appropriate specialist rather than treated as fresh-loan qualification.

## 4. General Pass Criteria

A test passes when the agent:

- Follows the specified business rules.
- Captures information accurately, including answers given out of order.
- Updates previously captured information when the customer clearly corrects it.
- Avoids asking questions that have already been answered.
- Disqualifies customers when mandatory conditions fail.
- Does not invent eligibility requirements, interest rates, or final loan approval.
- Uses polite, natural conversational language.
- Ends the call with the appropriate outcome.

## 5. Test Execution Summary

**Tests executed:** Update after completing the scenarios.

**Tests passed:** Update based on actual observed results.

**Tests failed:** Update based on actual observed results.

**Platform:** Retell AI

**Evidence:** Include accessible recording and transcript links for representative successful, disqualified, and special-case conversations where available.

## 6. Conclusion

The test suite evaluates the voice agent's ability to perform preliminary Loan Against Property qualification, enforce eligibility rules, handle realistic customer conversations, and route customers to the appropriate next step. Final completion status should reflect the actual outcomes of the executed tests.
