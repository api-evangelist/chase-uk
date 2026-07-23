---
name: Confirm funds availability (CBPII)
description: Set up an OBIE funds-confirmation consent, direct the PSU through SCA, then check whether a specified amount is available on a Chase UK account as an FCA-authorised CBPII.
api: openapi/obie-confirmation-funds-openapi.yaml
operations: [CreateFundsConfirmationConsents, GetFundsConfirmationConsentsConsentId, CreateFundsConfirmations]
---

# Confirm funds availability (Chase UK CBPII)

Prerequisite: FCA-authorised card-based payment instrument issuer (CBPII) onboarded to the Chase UK OBIE sandbox with FAPI OAuth2 client credentials and mutual-TLS.

1. **Get a client-credentials token** with scope `fundsconfirmations`.
2. **Create the funds-confirmation consent** — `CreateFundsConfirmationConsents` (POST `/funds-confirmation-consents`) referencing the PSU's `DebtorAccount`. Send `x-fapi-interaction-id`, `x-jws-signature`, `Authorization`; capture the `ConsentId`.
3. **Redirect the PSU** to authorise via authorization-code + PSD2 SCA; return with a PSU token bound to the `ConsentId`.
4. **Verify status** — `GetFundsConfirmationConsentsConsentId` — expect `Status: Authorised`.
5. **Check funds** — `CreateFundsConfirmations` (POST `/funds-confirmations`) with the `ConsentId` and the `InstructedAmount`; the response `Data.FundsAvailableResult.FundsAvailable` is a boolean. This is a point-in-time check and does not reserve funds.

Rules: consents expire per their `ExpirationDateTime`; a revoked or expired consent yields `403`/`400` in the OBIE `OBErrorResponse1` envelope (see `errors/chase-uk-problem-types.yml`).
