# Home Credit LAP Qualification Voice Agent

## Overview

An AI-powered voice agent built using Retell AI to conduct preliminary eligibility checks for Home Credit's Loan Against Property (LAP) offer.

The agent communicates with existing customers, collects eligibility information, identifies ineligible cases, and directs eligible prospects to a senior loan expert for further assistance.

## Objectives

- Automate preliminary customer qualification.
- Provide a natural and professional voice experience.
- Apply eligibility rules consistently.
- Identify cases requiring disqualification or loan-transfer support.
- Reduce repetitive manual qualification work.

## Key Features

- Customer identity verification.
- Explanation of the LAP offer of up to ₹75 lakh.
- Sequential eligibility information collection.
- Handling of interruptions, corrections, and out-of-order answers.
- Immediate disqualification when mandatory criteria fail.
- Separate handling for existing-loan transfer requests.
- Final handoff only after all eligibility checks pass.

## Eligibility Checks

1. Property type: Residential, commercial, or industrial.
2. Ownership: Sole or joint.
3. Original property documents: Must be available.
4. Loan amount: Maximum ₹75 lakh for this offer.
5. Occupation and income mode: Salaried or self-employed, with income received through a bank.
6. Estimated current property market value.
7. Loan tenure: 3–15 years.

## Technology

- Retell AI — voice-agent platform
- Large Language Model — conversational reasoning
- Speech recognition and text-to-speech — voice interaction

## Testing

The agent is tested against scenarios including:

- Successful preliminary qualification
- Agricultural property disqualification
- Cash-income disqualification
- Missing original property documents
- Loan requests above ₹75 lakh
- Existing-loan transfer requests
- Busy customers and callback preferences
- Out-of-order information and corrected answers

Actual results should be documented in `test-cases.md`.

## Important Note

This agent performs preliminary qualification only. It does not approve loans or guarantee eligibility for final credit approval.

## Author

Uday Krishna
