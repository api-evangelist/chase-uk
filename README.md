# Chase UK (chase-uk)

Chase UK is the digital retail bank operated in the United Kingdom by J.P. Morgan Europe Limited, a wholly owned subsidiary of JPMorgan Chase & Co. that launched the Chase consumer brand in the UK in September 2021. It is an app-only challenger bank with no physical branches or ATM estate, authorised and regulated by the FCA and PRA. As a UK account provider (ASPSP) it operates a dedicated Open Banking interface conformant to the OBIE Read/Write API Standard, exposing Account Information (AIS), Payment Initiation (PIS), and Confirmation of Funds (CBPII) services to FCA-authorised third-party providers.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/chase-uk/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/chase-uk/refs/heads/main/apis.yml)

## Tags

- Financial Services
- Banking
- Open Banking
- PSD2
- OBIE
- United Kingdom
- Payments
- Account Information
- Challenger Bank
- Fintech

## Timestamps

- **Created:** 2026-07-23
- **Modified:** 2026-07-23

## APIs

### Chase UK Account and Transaction Information API (AIS)

Chase UK's Account Information Service (AIS) dedicated interface, conformant to the OBIE Read/Write API Standard, letting FCA-authorised AISPs retrieve a consenting customer's account, balance, transaction, beneficiary, standing order, direct debit, and statement data. Access is gated behind developer onboarding and secured with FAPI OAuth2/OIDC, PSD2 SCA, and mutual-TLS.

- **Human URL:** [https://developer.openbanking-obie-sandbox.chase.co.uk/docs/](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)

#### Tags

- Account Information
- AISP
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-account-info-openapi.yaml) — shared OBIE Read/Write standard v4.0.1 (not a Chase-proprietary contract)
- [Documentation](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)
- [Info for TPPs](https://www.chase.co.uk/gb/en/information-for-tpps/)
- [Developer Portal](https://developer.openbanking-obie-sandbox.chase.co.uk/)

### Chase UK Payment Initiation API (PIS)

Chase UK's Payment Initiation Service (PIS) dedicated interface, conformant to the OBIE Read/Write API Standard, enabling FCA-authorised PISPs to create single immediate payments, future-dated payments, and standing orders to UK accounts on behalf of a consenting customer. Access is gated behind developer onboarding and secured with FAPI OAuth2/OIDC, PSD2 SCA, and mutual-TLS.

- **Human URL:** [https://developer.openbanking-obie-sandbox.chase.co.uk/docs/](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)

#### Tags

- Payment Initiation
- PISP
- Payments

#### Properties

- [OpenAPI](openapi/obie-payment-initiation-openapi.yaml) — shared OBIE Read/Write standard v4.0.1 (not a Chase-proprietary contract)
- [Documentation](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)
- [Info for TPPs](https://www.chase.co.uk/gb/en/information-for-tpps/)
- [Developer Portal](https://developer.openbanking-obie-sandbox.chase.co.uk/)

### Chase UK Confirmation of Funds API (CBPII)

Chase UK's Confirmation of Funds (CBPII) dedicated interface, conformant to the OBIE Read/Write API Standard, allowing an FCA-authorised card-based payment instrument issuer to check whether a specified amount is available on a consenting customer's account. Access is gated behind developer onboarding and secured with FAPI OAuth2/OIDC, PSD2 SCA, and mutual-TLS.

- **Human URL:** [https://developer.openbanking-obie-sandbox.chase.co.uk/docs/](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)

#### Tags

- Confirmation of Funds
- CBPII
- Open Banking

#### Properties

- [OpenAPI](openapi/obie-confirmation-funds-openapi.yaml) — shared OBIE Read/Write standard v4.0.1 (not a Chase-proprietary contract)
- [Documentation](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)
- [Info for TPPs](https://www.chase.co.uk/gb/en/information-for-tpps/)
- [Developer Portal](https://developer.openbanking-obie-sandbox.chase.co.uk/)

## Common Properties

- [Website](https://www.chase.co.uk/)
- [Developer Portal](https://developer.openbanking-obie-sandbox.chase.co.uk/)
- [Documentation](https://developer.openbanking-obie-sandbox.chase.co.uk/docs/)
- [Getting Started (Info for TPPs)](https://www.chase.co.uk/gb/en/information-for-tpps/)
- [Support](https://www.chase.co.uk/gb/en/support/contact-us/)
- [Terms of Service](https://www.chase.co.uk/gb/en/legal/general-terms-and-conditions/)
- [Privacy Policy](https://www.chase.co.uk/gb/en/legal/privacy-notice/)
- [LinkedIn](https://www.linkedin.com/company/chase/)

## Notes

Chase UK is app-only with no branch or ATM estate, so it does **not** publish OBIE Open Data APIs (ATMs / Branches / Personal & Business Current Accounts). Its only public API posture is the FAPI-secured OBIE Read/Write dedicated interface, reachable through the sandbox developer portal after FCA-authorised onboarding. TPP enquiries: open.banking@chase.com.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
