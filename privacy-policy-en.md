# PRIVACY POLICY — OMNICHAT AI

**Operator:** AAAI SOLUTIONS PTE. LTD., a company incorporated under the laws of the Republic of Singapore (hereinafter **"AAAI"**, **"we"**, **"us"**).
**Application:** OmniChat AI — the mobile application (iOS/Android) and its accompanying server-side services (collectively, the **"Service"**).
**Effective date:** 14 September 2026 · **Version:** 1.0
**Registered address:** 1002 JALAN BUKIT MERAH, #06-06, SINGAPORE 159456 · **Unique Entity Number (UEN):** [UEN]
**Privacy contact (Data Protection Officer):** anna@aaaisolutions.com

---

## OUR CORE COMMITMENT

> ### 🔒 Your data is never sold to third parties or used to train public AI models.
>
> Specifically, AAAI commits that:
>
> 1. We **do not sell, rent, or trade** your personal data, your message content, or your customers' message content to any third party, for any commercial purpose, including advertising.
> 2. We **do not use** your messages, knowledge documents (AI Brain), product catalogs, or any other content you place in the Service to train, fine-tune, or improve any public or shared AI model — whether ours or an AI provider's.
> 3. We access AI providers only through their **enterprise/API terms**, under which the provider is contractually bound **not to use data submitted via the API to train its models** (see Section 6).
> 4. Content you provide is used **solely to generate replies for your own store** — fully isolated per account; no account can ever access another account's data.
> 5. The Service **displays no advertising** and contains no advertising or cross-app tracking SDKs.

---

## 1. Scope and Our Role

1.1. This Policy explains how AAAI collects, uses, stores, shares, and protects personal data when you use the Service. It is drafted in accordance with the Singapore Personal Data Protection Act 2012 (PDPA) and is designed to satisfy the disclosure requirements of the Apple App Store (App Privacy / Privacy Nutrition Labels, Guideline 5.1) and Google Play (Data Safety, User Data Policy).

1.2. There are two categories of data subjects:

- **Users** — store or business owners who register an OmniChat AI account. For your account data, AAAI is the **data controller** (an "organisation" under the PDPA).
- **Your Customers** — people who message the channels (Facebook, Instagram, WhatsApp, Telegram, Zalo, LINE, Viber, WeChat, X, Threads, YouTube, TikTok, etc.) you have linked. For those conversations, **you are the data controller** and AAAI acts solely as a **data processor (data intermediary)** on your instructions.

1.3. The Service is intended for business use and is **not directed at persons under 18**. We do not knowingly collect children's data; if we discover we have, we delete it immediately.

## 2. Data We Collect

### 2.1. Account and Login Information

| Data | Purpose | How collected |
|---|---|---|
| Email address | Account identifier, login, password recovery, service and renewal notices | Entered by you at sign-up |
| Password | Authentication | **One-way salted hash using a standard algorithm** before storage; we **never store passwords in plain text** and cannot read them back |
| Display name / store name, UI language, time zone | Personalization, localization in 8 languages | Entered by you in Settings |
| Session token (JWT) | Keeping you signed in | Issued by our server; stored in the OS secure storage (iOS Keychain / Android Keystore-backed storage) |

If you sign in with Apple or Google (where offered), we receive only the email and identifier returned by that provider; we **never** receive your password for those platforms.

### 2.2. Social Media Access Tokens (Channel Linking)

To reply to messages on your behalf, the Service needs you to authorize your platform accounts. The mechanism is as follows:

- **Only official OAuth 2.0** flows of each platform are used (Meta Graph API for Facebook/Instagram/WhatsApp Business, Zalo OA, LINE Messaging API, TikTok Business, X API, YouTube Data API, etc.), or **credentials issued by the platform itself to developers** (e.g., a Bot Token from Telegram BotFather, a LINE Channel Access Token, a Viber Auth Token, a WeChat Official Account AppID/AppSecret). The app **never asks for and never displays a password field** for your social media accounts, and performs **no web scraping** of any kind.
- The consent screen opens in the secure system browser (`ASWebAuthenticationSession` on iOS, Chrome Custom Tabs on Android). The app cannot read what you type on the platform's page.
- **Permissions are requested at the minimum level**: only the read and send rights for messages/comments on the pages, business accounts, or bots you choose to link.
- After you consent, the platform sends the authorization code **directly to AAAI's servers**, which exchange it for the access/refresh token. **Tokens never pass through your phone** and are not stored on the device.
- Tokens are **encrypted with AES-256-GCM** using a separately managed key (not stored with the database) before storage; only the messaging service can decrypt them when calling the platform API.
- You may **disconnect or delete any channel at any time** in the Channels tab. The token is then permanently erased from our systems and the webhook is unregistered. You may also revoke access directly in the platform's settings (e.g., Facebook → Settings → Business Integrations).

### 2.3. Conversation Content and Your Customers' Data

Once a channel is linked, the platform forwards to our servers (via signature-verified webhooks):

- Text messages, images, and attachments sent by your customers, and the replies sent out (generated by AI or typed manually by you);
- Platform-assigned identifiers of the customer (sender ID, display name, avatar where the platform provides it) — we **do not** query any additional profile data beyond what the platform attaches to the message;
- Information customers volunteer in conversation to complete an order (e.g., phone number, delivery address) — stored in the Unified Inbox and Orders section for you to process.

This data **belongs to you**. We process it only to: display it in the Unified Inbox, generate automatic replies, detect order closed/cancelled events to notify you, and compile analytics for your account only.

### 2.4. AI Brain Data (Knowledge Base)

Product catalogs and prices, shipping/return policies, business hours, address, promotions, FAQs, documents, images, videos, links, and text you upload to "teach" the AI. This data is used only as context when generating replies for your store. When you delete a document, **all data the AI extracted from that document is deleted with it** (cascade delete).

### 2.5. Device Data and Push Notifications

- Push token (APNs / Firebase Cloud Messaging) for notifications about new messages, closed orders, cancelled orders, handover requests, and renewal reminders;
- Device type, OS version, app version, language — for compatibility and diagnostics;
- Technical crash logs that **do not contain message content**.

We do **not** collect precise location, contacts, photos/media other than files you actively choose to upload, or advertising identifiers (IDFA / Advertising ID).

### 2.6. Payment Data

- **In-app purchases (iOS/Android):** transactions are processed by the Apple App Store / Google Play. Through RevenueCat we receive: an anonymized transaction ID, the plan purchased, start/expiry dates, and renewal status. **We never have access to your card number, bank details, or billing address.**
- **Web payments (Stripe):** card numbers, GrabPay, PayNow, Google Pay, etc. are entered directly on a Stripe-hosted, PCI-DSS Level 1 secured payment page. We store only your Stripe customer ID, subscription status, and the last four digits of the card (if provided by Stripe) for display.
- Invoices and transaction records are retained for the period required by Singapore accounting and tax law (currently 5 years).

### 2.7. Usage Data

Number of AI messages used in the period (to enforce PRO plan quotas), number of linked channels, closed/cancelled order events per platform (for the Analytics tab). We do not use third-party behavioral analytics tools for advertising purposes.

## 3. Purposes and Legal Bases for Processing

| Purpose | Legal basis (PDPA / GDPR where applicable) |
|---|---|
| Providing the Service: login, channel linking, receiving/sending messages, AI reply generation, inbox, analytics | Performance of our contract with you; your consent when linking channels |
| Billing, renewals, quotas, expiry reminders (3 days before and on the expiry date) | Performance of contract; legal obligation (accounting) |
| Push notifications about account activity | Performance of contract; you may disable them in OS Settings |
| Security, fraud/abuse prevention, diagnostics | Legitimate interests of AAAI and of you |
| Compliance with requests from competent authorities | Legal obligation |
| Marketing emails (if any) | Consent; may be withdrawn at any time via the unsubscribe link |

We do **not** make automated decisions with significant legal effects about you; the AI only drafts replies within the parameters you configure, and you can always intervene manually.

## 4. Data Sharing — Sub-processors

We share data only with providers necessary to operate the Service, each bound by a data processing agreement and permitted to process only on our instructions:

| Sub-processor | Role | Data involved |
|---|---|---|
| OpenAI (API) | AI reply generation | Conversation context and knowledge needed for each reply (Section 6) |
| Apple (App Store, APNs) / Google (Play, Firebase Cloud Messaging) | App distribution, in-app billing, push delivery | Push tokens; anonymized transactions |
| RevenueCat | Subscription state management on iOS/Android | Anonymized account identifier, plan status |
| Stripe | Web payments | Payment data collected directly by Stripe |
| Messaging platforms you link (Meta, Telegram, Zalo, LINE, Viber, WeChat, X, TikTok, YouTube, etc.) | Two-way message delivery on your instructions | Reply content, media you allow the AI to send |
| Cloud hosting and storage provider Amazon Web Services (AWS), Singapore | Hosting and operations | All data, encrypted at rest |
| Transactional email service Amazon SES | Verification, password reset, renewal reminder emails | Email address, notice content |

We may also disclose data when **required by law** (court order or lawful request from a competent authority, after verifying its validity) or in a **corporate restructuring** (the transferee must continue to honor this Policy; you will be notified in advance). **In no case is data sold.**

## 5. Apple App Privacy and Google Play Data Safety Disclosure Table

| Data type | Collected? | Linked to identity? | Used for tracking? | Purpose |
|---|---|---|---|---|
| Email | Yes | Yes | No | App functionality, account management |
| Name / store name | Yes | Yes | No | App functionality |
| Messages (from your customers) | Yes | Yes | No | App functionality |
| Photos/videos/documents you upload | Yes | Yes | No | App functionality |
| Purchase history (subscriptions) | Yes | Yes | No | App functionality |
| Payment info (card numbers) | **No** (handled by Apple/Google/Stripe) | — | — | — |
| Device ID / push token | Yes | Yes | No | App functionality |
| Usage data (AI quota, order events) | Yes | Yes | No | App functionality, internal analytics |
| Crash logs | Yes | No | No | Diagnostics |
| Location, contacts, IDFA/Advertising ID, health data, financial data | **No** | — | — | — |

All data is **encrypted in transit** (TLS 1.2 or higher) and users can **request deletion** directly in the app (Section 8).

## 6. How Message Content Is Processed and Encrypted When Communicating with AI APIs

6.1. **Data flow.** When your customer sends a message, our server assembles a "context" consisting of: system instructions (the tone and rules you configured), the relevant portion of your AI Brain knowledge, and the most recent messages of that conversation. This context is sent to the AI provider's API to generate a reply, which is then delivered back to the messaging platform.

6.2. **Encryption of inputs and outputs.**
- Every connection — phone ↔ AAAI servers ↔ AI API ↔ messaging platform — is encrypted with **TLS 1.2 or higher (HTTPS)** using validated certificates; no data travels over an unencrypted connection.
- Platform webhooks are accepted only when the **signature/secret token is valid**; unauthenticated requests are rejected.
- Message content, AI Brain knowledge, and media files are stored on infrastructure with **encryption at rest (AES-256)**; platform access tokens carry an additional application-layer encryption (AES-256-GCM, Section 2.2).
- Push tokens and payment information are never sent to AI APIs.

6.3. **Data minimization toward the AI.** We send only the conversation excerpt and knowledge needed for the current reply; we **do not** send emails, passwords, tokens, payment data, or data belonging to other stores. The customer's platform identifier is replaced with an internal identifier before sending.

6.4. **No training.** We use the enterprise API of our AI provider (currently OpenAI). Under the provider's API terms, **data submitted via the API is not used to train or improve their models**. The provider may temporarily retain API logs for a limited period (per its published policy, up to 30 days) solely for abuse detection, after which they are deleted. We will enable **Zero Data Retention** as soon as the provider grants it for our account. AAAI itself trains no models on your data.

6.5. **Per-account isolation.** Each account's knowledge base and conversations are logically isolated by account identifier on every query; one store's AI can never "see" another store's data.

6.6. **Human control.** You can pause the AI per conversation (automatically when you reply manually), disable the AI per channel, or have the AI hand over to a human when a customer requests it.

## 7. Security

- Least-privilege access controls; AAAI staff access data only when needed for technical support you request, and every access is logged.
- Encryption keys, secrets, and configuration are managed separately from the database and source code.
- Regular encrypted backups; restoration testing.
- **Breach notification:** if a data incident likely to cause significant harm occurs, we will notify the Personal Data Protection Commission of Singapore (PDPC) within 3 calendar days of assessment and notify you without undue delay, with mitigation guidance.
- No system is absolutely secure; you are responsible for keeping your password confidential and protecting your device.

## 8. Retention and Deletion

| Data | Retention period |
|---|---|
| Account, AI Brain, conversations, media | For as long as the account is active |
| Platform access tokens | Until you disconnect the channel or delete the account — erased immediately |
| Conversations you delete in the Inbox | Deleted immediately from primary systems; backups overwritten within 30 days |
| Deleted account | All data permanently deleted within **30 days** (grace period to protect against accidental deletion); backups overwritten within the following 30 days |
| Transaction records / invoices | 5 years under Singapore law, held separately from conversation data |
| Technical logs | Up to 90 days |

**Delete account & data in the app:** go to **Settings → Delete Account & Data** (a clearly visible button; no need to contact support). Deletion will: unregister webhooks and erase tokens for all channels, delete AI Brain, conversations, media, push tokens, and profile information. Any active subscription must be cancelled separately through Apple/Google (see the EULA) — deleting the account does not automatically refund the unused portion. You may also request deletion via the DPO email.

## 9. Your Rights

Under the PDPA (and the GDPR/UK GDPR or CCPA if you reside in those jurisdictions), you have the right to:

- **Access** and obtain a copy of your personal data;
- **Correct** inaccurate data (directly in Settings or by request);
- **Delete** data (Section 8);
- **Withdraw consent** (disconnect channels, disable notifications, unsubscribe from marketing emails) — withdrawal may render some features unavailable;
- **Data portability**: export conversations and AI Brain in a machine-readable format on request;
- **Object to / restrict** certain processing;
- **Lodge a complaint** with the competent data protection authority (in Singapore: PDPC, www.pdpc.gov.sg).

We respond within **30 days** and free of charge unless a request is manifestly unfounded or excessive. We may require identity verification before acting.

## 10. Your Responsibilities Toward Your Customers

Because you are the data controller for conversations with your customers, you undertake to:

- Have a lawful basis and appropriate notices for collecting and processing customers' messages with automated tools, under the laws where you operate;
- Comply with platform terms (e.g., Meta policies on disclosing bot interactions, the WhatsApp/Messenger 24-hour messaging window, Zalo OA messaging rules, etc.);
- Not upload unnecessary sensitive personal data of third parties (health, financial, government ID data, etc.) to AI Brain;
- Handle and respond to privacy requests from your customers; we will assist through the conversation deletion and data export tools.

## 11. International Data Transfers

Data may be stored and processed in Singapore and in regions where our sub-processors operate (including the United States and the European Union). All transfers are protected by contracts containing data-protection terms equivalent to the PDPA (for data within GDPR scope: the EU Standard Contractual Clauses).

## 12. Cookies and Tracking Technologies

The mobile app does not use cookies. The web payment site uses only strictly necessary cookies for the login session and Stripe's fraud-prevention cookies. We use no advertising cookies and honor "Do Not Track" signals where applicable.

## 13. Changes to This Policy

For material changes (e.g., adding a sub-processor, changing a purpose), we will notify you in the app and/or by email **at least 15 days** before they take effect. Continued use of the Service after the effective date constitutes acceptance of the new version; if you disagree, you may delete your account. Prior versions are archived and available on request.

## 14. Contact

- **Data Protection Officer:** anna@aaaisolutions.com
- **Support:** anna@aaaisolutions.com
- **Post:** AAAI SOLUTIONS PTE. LTD., 1002 JALAN BUKIT MERAH, #06-06, SINGAPORE 159456, Singapore

This Policy is drafted in English; where translations exist, the English version prevails in case of conflict, unless the law of your place of residence provides otherwise.
