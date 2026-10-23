# Plan: Using an AI email agent to find SMEs that need agentic applications

> **Setup (as you described it):** you use an **AI email agent** to do the outreach. The **SMEs are your prospects**: businesses that could use agentic applications (AI agents that do work for them). The goal is to find the right SMEs, let your agent contact them, and turn replies into calls and projects.

---

## Step 1. Decide what you sell and to whom (1 to 2 days)

Pick **one niche** and **one or two agentic apps** you can show quickly. SMEs buy a clear result, not "AI".

| SME niche | Repetitive work they have | Agentic app you could offer |
|---|---|---|
| Clinics / dental / beauty | Bookings, reminders, FAQs on WhatsApp and email | Booking and customer-reply agent |
| Real estate agencies | Lead enquiries, viewing scheduling | Lead qualifying and follow-up agent |
| Small e-commerce shops | Order questions, refunds, product listings | Customer-service and listing agent |
| Accounting / admin services | Chasing documents, data entry from invoices | Document collection and data-entry agent |
| Trading / logistics | Quotes, RFQs, shipment updates | Quote-drafting and status-update agent |

Write a one-line **Ideal Customer Profile (ICP)**, for example:
*"Clinics with 5 to 50 staff in [your city] that handle bookings manually and have no in-house tech team."*

## Step 2. Build the SME prospect list (2 to 3 days)

Your email agent is only as good as the list you give it.

1. **Google Maps**: search "dental clinic [city]". It gives name, website and phone. This is the easiest start.
2. **Business directories**: your country's company registry (for example SSM in Malaysia or ACRA in Singapore), Yellow Pages, and industry associations or chambers of commerce.
3. **LinkedIn**: filter companies by industry, location and size (11 to 50 or 51 to 200 staff). Find the owner, founder or operations manager.
4. **Platforms**: Shopee or Lazada sellers, or Shopify stores, for e-commerce.
5. **Email finders** (optional): Apollo.io, Hunter.io, Snov.io. Start with the free tiers.

Keep everything in **one sheet** that your agent can read from and write to:
`Company | Industry | City | Size | Website | Contact name | Role | Email | Pain signal | Score | Status | Last contact | Notes`

Start with **100 SMEs**.

## Step 3. Qualify them, using the agent to help (1 day)

The agent can visit each website or listing and fill in the **Pain signal** column. Score each company 0 to 3:
- **+1** for manual processes that are visible, such as "book by WhatsApp", "email us for a quote", or a contact form only.
- **+1** if they are hiring admin, customer-service or data-entry staff (work an agent could take on).
- **+1** if a decision maker can be reached (owner or manager, not only info@).

Send the first emails only to companies scoring **2 to 3** (about 30).

## Step 4. Set up your email agent safely (2 to 3 days, alongside Steps 2 and 3)

**Sending setup (so you don't land in spam):**
- Use a **separate outreach domain** (for example `getyourbrand.com`), not your main one.
- Set up SPF, DKIM and DMARC, and **warm up** the inbox for 1 to 2 weeks.
- Limit sending to **20 to 30 emails a day per inbox** at first.

**Agent rules:**
- Each email gets a **personal first line** based on the pain signal (for example *"I saw patients book through WhatsApp only"*).
- **You approve the first 50 emails yourself** before they go out. After that, spot-check them.
- The agent **stops automatically** when someone replies, unsubscribes or bounces.
- Positive replies go to you right away. The agent can suggest times but should not promise prices or features.
- Follow your local law (for example PDPA in Malaysia or Singapore): business contacts only, say who you are, and include an easy opt-out.

**Tools:** Gmail or Google Workspace with a sequencing tool (Instantly, Lemlist, Apollo) or your own agent, connected to the sheet from Step 2.

## Step 5. Messages and sequence (start once the domain is warm)

**First email (short, about their problem):**

> Subject: [Clinic name]'s bookings
>
> Hi [Name],
>
> I noticed [personal pain signal, for example "patients book through WhatsApp and phone only"]. Clinics your size often spend 1 to 2 hours a day just answering and rescheduling.
>
> We build small AI agents that handle this for you, such as replying to enquiries, booking slots and sending reminders, while your staff stay in control.
>
> Would a 15-minute call to see a short demo be useful?
>
> [Your name]
>
> *If this isn't relevant, just reply "no" and I won't email again.*

**Follow-ups:** day 3 (a short bump), day 7 (a 1 to 2 minute demo video for their niche), day 14 (final note). Stop after 3.

**Tip:** your own email agent is proof that you build agents. You can say so in follow-ups: *"This email was sent by an AI agent we built and checked by me."* Be honest and keep it as an optional line you can test.

**Track:** sent, replied, call booked, proposal, won. Aim for 5 to 10% replies with a well-targeted list.

## Step 6. Calls, pilots and case studies (weeks 2 to 6)

- On calls, ask: *Which task takes the most time each day? Who does it now? What tools do you use (WhatsApp, Gmail, Excel, POS)?*
- Offer a **small paid or free pilot** for one workflow (2 to 4 weeks) with a clear measure, such as hours saved or faster reply time.
- Turn each good pilot into a **one-page case study** and give it to your agent for the next round of emails.
- After 30 to 50 conversations, keep the niche if it is working or try the next one.

---

## Architecture of the outreach system

```
 Sources                    Data                  AI agent                    Sending                 Human
 ─────────                  ────                  ────────                    ───────                 ─────
 Google Maps ─┐                              ┌─► Research: read site,     ┌─► Outreach domain     ┌─► Approve drafts
 LinkedIn ────┼─► Lead sheet / CRM ──────────┤   find pain signal, score   │   (SPF/DKIM/DMARC,    │   (first 50, then
 Directories ─┤   (Google Sheets or          │                            │   warm-up, 20-30/day) │   spot checks)
 Apollo/Hunter┘    Airtable, HubSpot free)   └─► Write: personal email ───┘                       │
                        ▲                         + 3 follow-ups               Sequencer ──────────┤
                        │                                                     (Instantly/Lemlist/  └─► Take calls,
                        │                                                      Apollo or Gmail API)     run pilots
                        │                                                           │
                        └──────────── status updates: sent / replied / bounced / opted out ◄─┘
                                      (reply or opt-out = stop the sequence)

 Orchestration: n8n, Make or Zapier runs the steps on a schedule and moves rows between stages.
```

| Layer | Job | Suggested tools |
|---|---|---|
| Lead sources | Find SMEs and contacts | Google Maps, LinkedIn, local registries and directories, Apollo.io, Hunter.io |
| Data store | One row per SME with stage, score, notes, last contact | Google Sheets to start, then Airtable or HubSpot (free CRM) |
| Research agent | Read the website, write the pain signal, give a 0 to 3 score | An LLM (for example Claude) with web-page fetching |
| Writer agent | Draft the first email and follow-ups from the pain signal and a template | Same LLM, with a fixed prompt and the case-study library |
| Approval step | You approve drafts before sending | A "Ready to send" column in the sheet, or Gmail drafts |
| Sending | Sends at a safe rate, handles follow-ups, detects replies and bounces | Separate domain plus Instantly, Lemlist, Apollo sequences or the Gmail API |
| Orchestration | Connects everything and runs it on a schedule | n8n (free to self-host), Make or Zapier |
| Feedback loop | Replies, opt-outs and bounces update the sheet; won pilots become case studies for the writer | The sequencer's webhooks into n8n or Make |

**Guardrails built into the design:** a daily send cap, human approval, automatic stop on reply or opt-out, a suppression list that is never emailed again, and the opt-out line in every email (PDPA).

**Build order:** run it by hand with a sheet and Gmail first, then add the AI research and writing, then automate with n8n or Make once the emails get replies.

---

## Your first-week checklist

| Day | Task |
|---|---|
| 1 | Pick one niche and one agentic app; write your ICP sentence |
| 2 | Buy the outreach domain; set up SPF, DKIM and DMARC; start warm-up |
| 3 | Pull 50 SMEs from Google Maps and directories into the sheet |
| 4 | Pull 50 more (LinkedIn or email finders); find names and emails |
| 5 | Let the agent fill in pain signals; score everyone; pick the top 30 |
| 6 | Record a 1 to 2 minute demo; write the first email and follow-ups |
| 7 | Have the agent draft the first 30 emails; review and approve them, ready to send once warm-up is done |
