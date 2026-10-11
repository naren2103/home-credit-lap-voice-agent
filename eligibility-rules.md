# Eligibility Rules — Home Credit LAP Qualification Voice Agent

## 1. Overview

The Home Credit Loan Against Property (LAP) Qualification Voice Agent performs preliminary eligibility checks for existing Home Credit customers interested in a Loan Against Property offer.

The maximum loan amount under this offer is **₹75,00,000 (₹75 lakh)**.

The agent collects the required information, applies the eligibility rules, identifies disqualified customers, and directs eligible prospects to a senior loan expert.

**Important:** This is a preliminary eligibility check, not a final loan approval or credit decision.

---

## 2. Eligibility Criteria

### Rule 1: Property Type

**Information required:** Type of property offered for the loan.

| Property type | Decision |
|---|---|
| Residential | Eligible |
| Commercial | Eligible |
| Industrial | Eligible |
| Agricultural | Not eligible |

**Action:** If the property is agricultural, politely explain that it does not meet the eligibility criteria for this offer and end the call.

### Rule 2: Property Ownership

**Information required:** Whether the property is solely owned or jointly owned.

| Ownership | Decision |
|---|---|
| Sole ownership | Eligible |
| Joint ownership | Eligible |

**Action:** Accept either ownership type. Do not disqualify a customer solely because the property is jointly owned.

### Rule 3: Original Property Documents

**Information required:** Whether the original property documents are available.

| Document status | Decision |
|---|---|
| Original documents available | Eligible |
| Original documents unavailable; only photocopies available | Not eligible |

**Action:** If the customer cannot provide the original documents, politely explain that the mandatory requirement is not met and end the call.

### Rule 4: Desired Loan Amount

**Information required:** The amount the customer wants to borrow.

| Requested amount | Decision |
|---|---|
| ₹75 lakh or less | Continue eligibility checks |
| More than ₹75 lakh; customer accepts ₹75 lakh | Continue eligibility checks |
| More than ₹75 lakh; customer refuses the ₹75 lakh limit | End the call |

**Action:** If the customer requests more than ₹75 lakh, explain that the offer has a maximum limit of ₹75 lakh and ask whether they would like to proceed with that amount.

Do not automatically disqualify the customer for initially requesting more than the offer limit.

### Rule 5: Occupation and Income Mode

**Information required:** Occupation and how the customer receives income.

| Occupation | Income mode | Decision |
|---|---|---|
| Salaried | Received through a bank | Eligible |
| Self-employed | Received through a bank | Eligible |
| Salaried or self-employed | Received entirely in cash | Not eligible |

**Action:** Both salaried and self-employed customers can qualify, provided their income is received through a bank.

If income is received in cash, politely explain that the customer does not meet the eligibility criteria and end the call.

If the customer provides only their occupation or only their income mode, ask for the missing information.

### Rule 6: Property Market Value

**Information required:** Estimated current market value of the property.

**Action:** Ask the customer for their estimated current market value and record the response.

No minimum property market value threshold is specified in the assignment. Do not invent a minimum value or disqualify the customer based on an unsupported threshold.

### Rule 7: Loan Tenure

**Information required:** The customer's preferred loan repayment tenure.

| Requested tenure | Decision |
|---|---|
| Less than 3 years | Not eligible |
| 3–15 years, inclusive | Eligible |
| More than 15 years | Not eligible |

**Action:** The permitted tenure is from 3 to 15 years, inclusive. If the requested tenure falls outside this range, explain the permitted range and end the call if the customer cannot proceed within it.

---

## 3. Existing Loan and Loan-Transfer Handling

The agent must distinguish between a fresh Loan Against Property request and a request involving an existing loan.

**Transfer-related triggers include:**
- The customer already has a loan secured against the property.
- The customer wants to transfer an existing property loan.
- The customer wants to reduce their current EMI through a loan transfer.

**Action:**
1. Recognize the existing-loan or transfer requirement.
2. Explain politely that a loan-transfer specialist will contact the customer.
3. End the current qualification call.
4. Do not continue the fresh-loan qualification process or declare the customer eligible for a fresh loan.

This routing rule takes priority whenever transfer intent is identified.

---

## 4. Customer Busy or Unavailable

If the customer says they are busy or cannot speak:

1. Acknowledge their situation politely.
2. Ask for a suitable callback time if they have not already provided one.
3. Confirm the preferred callback time.
4. End the current call without starting the eligibility questionnaire.

The agent must not claim that a callback has been scheduled unless an actual scheduling mechanism is configured.

---

## 5. Conversation and Information-Collection Rules

The agent must follow these rules throughout the conversation:

- Collect all seven required eligibility categories.
- Capture relevant information even when the customer provides it out of order.
- Do not ask again for information that the customer has already clearly provided.
- If the customer provides multiple details in one response, record each applicable detail.
- If the customer corrects an earlier answer, update the stored information using the latest clear correction.
- If an answer is unclear or incomplete, ask a concise clarification question.
- Check for existing-loan or transfer intent whenever it is mentioned.
- Stop the fresh-loan process immediately when a mandatory disqualifying condition is confirmed.
- Do not invent eligibility requirements, minimum property values, interest rates, or guaranteed approval outcomes.

---

## 6. Final Decision Logic

### Outcome A: Preliminary Qualification Passed

The agent may provide the preliminary qualification outcome only when:

- All seven eligibility categories have been collected.
- All mandatory eligibility criteria are satisfied.
- Any requested amount above ₹75 lakh has been reduced to the offer limit with the customer's agreement.
- No loan-transfer requirement has been identified.

**Action:** Explain that a senior loan expert will contact the customer to discuss exact interest rates and next steps. Clarify that this is not final approval.

### Outcome B: Customer Disqualified

If any mandatory eligibility condition fails:

1. Explain the relevant reason politely.
2. Do not continue asking the remaining eligibility questions.
3. Do not offer the standard senior-loan-expert handoff.
4. End the call courteously.

### Outcome C: Loan-Transfer Request

If the customer needs an existing-loan transfer or EMI-reduction service:

1. Explain that a loan-transfer specialist will contact them.
2. End the current call.
3. Do not classify the request as a fresh-loan qualification.

### Outcome D: Customer Refuses the Offer Limit

If the customer requests more than ₹75 lakh and refuses to proceed with ₹75 lakh:

1. Acknowledge their preference.
2. Explain the maximum limit of the offer.
3. End the call politely.

---

## 7. Test Scenarios

| Test ID | Scenario | Expected outcome |
|---|---|---|
| TC-01 | All eligibility criteria satisfied | Preliminary qualification and senior expert handoff |
| TC-02 | Agricultural property | Immediate disqualification |
| TC-03 | Income received in cash | Immediate disqualification |
| TC-04 | Original documents unavailable | Immediate disqualification |
| TC-05A | Requests ₹90 lakh and accepts ₹75 lakh | Continue eligibility checks |
| TC-05B | Requests ₹90 lakh and refuses ₹75 lakh | End call |
| TC-06 | Existing property loan or EMI-reduction transfer request | Refer to loan-transfer specialist and end call |
| TC-07 | Customer is busy | Capture callback preference and end current call |
| TC-08 | Customer provides answers out of order | Record details and ask only for missing information |
| TC-09 | Customer corrects an earlier answer to agricultural property | Update the property type and disqualify |
| TC-10 | Jointly owned residential property | Accept ownership type |
| TC-11 | Tenure below 3 or above 15 years | Reject out-of-range tenure |
| TC-12 | Market value provided | Record the estimate without inventing a minimum threshold |

**Testing note:** Record the actual outcome of every test separately. Mark a test as passed only after verifying the call transcript or observed behavior.

---

## 8. Limitations and Disclaimer

The voice agent performs preliminary qualification only. Final loan eligibility, property valuation, documentation verification, interest rates, and loan approval remain subject to the lender's applicable assessment and processes.

The agent must not promise approval, guarantee loan terms, or represent the preliminary result as a final credit decision.
