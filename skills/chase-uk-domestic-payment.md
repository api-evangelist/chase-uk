---
name: Initiate a domestic payment (PIS)
description: Create an OBIE domestic-payment consent, confirm funds, direct the PSU through SCA, and submit a single immediate domestic payment on Chase UK as an FCA-authorised PISP.
api: openapi/obie-payment-initiation-openapi.yaml
operations: [CreateDomesticPaymentConsents, GetDomesticPaymentConsentsConsentId, GetDomesticPaymentConsentsConsentIdFundsConfirmation, CreateDomesticPayments, GetDomesticPaymentsDomesticPaymentId]
---

# Initiate a domestic payment (Chase UK PIS)

Prerequisite: FCA-authorised PISP onboarded to the Chase UK OBIE sandbox with FAPI OAuth2 client credentials and a mutual-TLS certificate.

1. **Get a client-credentials token** with scope `payments`.
2. **Create the payment consent** — `CreateDomesticPaymentConsents` (POST `/domestic-payment-consents`) with `Data.Initiation` (DebtorAccount optional, CreditorAccount, InstructedAmount, remittance info). Required headers include `x-idempotency-key` (unique per logical request, valid 24h), `x-jws-signature`, `x-fapi-interaction-id`, `Authorization`. Capture the `ConsentId`.
3. **Redirect the PSU** to authorise via authorization-code + PSD2 SCA; return with a PSU token bound to the `ConsentId`.
4. **Verify status** — `GetDomesticPaymentConsentsConsentId` — expect `Status: Authorised`.
5. **Confirm funds** (optional) — `GetDomesticPaymentConsentsConsentIdFundsConfirmation` returns whether funds are available.
6. **Submit the payment** — `CreateDomesticPayments` (POST `/domestic-payments`) echoing the same `Data.Initiation` and the `ConsentId`, with a fresh `x-idempotency-key` and `x-jws-signature`. Capture `DomesticPaymentId`.
7. **Track settlement** — poll `GetDomesticPaymentsDomesticPaymentId` for `Status` transitions.

Rules: replaying an `x-idempotency-key` with a different body returns `409`. Business-rule rejections surface as `422` with OBIE `ErrorCode`s (see `errors/chase-uk-problem-types.yml`).
