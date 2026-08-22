# Chase UK (chase-uk)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
