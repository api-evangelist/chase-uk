---
name: Read a customer's accounts, balances and transactions (AIS)
description: Set up an OBIE account-access consent, direct the PSU through SCA, then read a Chase UK customer's accounts, balances and transactions as an FCA-authorised AISP.
api: openapi/obie-account-info-openapi.yaml
operations: [CreateAccountAccessConsents, GetAccountAccessConsentsConsentId, GetAccounts, GetAccountsAccountIdBalances, GetAccountsAccountIdTransactions]
---

# Read accounts, balances and transactions (Chase UK AIS)

Prerequisite: you are an FCA-authorised AISP onboarded to the Chase UK OBIE sandbox, holding valid FAPI OAuth2 client credentials and a mutual-TLS (eIDAS QWAC/OBWAC) transport certificate.

1. **Get a client-credentials token** with scope `accounts` (see `scopes/chase-uk-scopes.yml`), authenticating with mTLS / private_key_jwt.
2. **Create the consent** — `CreateAccountAccessConsents` (POST `/account-access-consents`) with the `Permissions` you need (e.g. `ReadAccountsDetail`, `ReadBalances`, `ReadTransactionsDetail`) and optional expiration/transaction-window. Send required headers: `x-fapi-interaction-id`, `x-jws-signature`, `Authorization`. Capture the returned `ConsentId`.
3. **Redirect the PSU** to authorise the consent via the authorization-code flow with PSD2 SCA. On return you hold a PSU access token bound to the `ConsentId`.
4. **Confirm consent status** — `GetAccountAccessConsentsConsentId` — expect `Status: Authorised` before reading data.
5. **List accounts** — `GetAccounts` (PSU token) to obtain each `AccountId`.
6. **Read balances** — `GetAccountsAccountIdBalances` per `AccountId`.
7. **Read transactions** — `GetAccountsAccountIdTransactions`, paging via the `Links.Next` cursor and filtering with `fromBookingDateTime` / `toBookingDateTime`.

Rules: idempotency is not required on GETs but the consent POST honours `x-idempotency-key`. Handle errors per the OBIE `OBErrorResponse1` envelope (see `errors/chase-uk-problem-types.yml`); a `403` means the consent lacks the permission for that resource.
