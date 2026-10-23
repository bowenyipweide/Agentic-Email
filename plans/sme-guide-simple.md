# The super simple guide

## The big idea (in one sentence)

**You have a robot that writes emails. You use it to find small shops and companies that need robots too, and you build those robots for them.**

- **You** = the one who builds helper robots (we call them "agents").
- **Your email robot** = your helper that writes and sends emails for you.
- **SMEs** = small and medium businesses, like a clinic, a small online shop or a property agent.
- **What they need** = a helper robot that does their boring, repeated work.

---

## How the whole thing works (the architecture) 🧩

Think of it like a little factory with 6 rooms. Each room does one job and passes its work to the next room.

```
  ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
  │ 1. FINDER 🔍 │ ──► │ 2. LIST 📒   │ ──► │ 3. CHECKER ⭐ │
  │ finds shops  │     │ the Google   │     │ reads their  │
  │ on Maps and  │     │ Sheet with   │     │ website and  │
  │ LinkedIn     │     │ every shop   │     │ gives stars  │
  └──────────────┘     └──────────────┘     └──────┬───────┘
                                                   │
                                                   ▼
  ┌──────────────┐     ┌──────────────┐     ┌──────────────┐
  │ 6. YOU 🙋    │ ◄── │ 5. SENDER 📮 │ ◄── │ 4. WRITER ✍️  │
  │ check emails │     │ sends 20 to  │     │ AI writes a  │
  │ and take the │     │ 30 a day and │     │ personal     │
  │ calls        │     │ watches for  │     │ email for    │
  │              │     │ replies      │     │ each shop    │
  └──────────────┘     └──────────────┘     └──────────────┘
         ▲                                         │
         └──────── you say OK before it sends ─────┘
```

**What each room is, in real life:**

| Room | What it does | Tool you can use |
|---|---|---|
| 1. Finder 🔍 | Finds shops and their emails | Google Maps, LinkedIn, Apollo.io or Hunter.io |
| 2. List 📒 | Remembers every shop and what happened | Google Sheets |
| 3. Checker ⭐ | Reads each website and gives stars | An AI (like Claude) |
| 4. Writer ✍️ | Writes a short, personal email | An AI (like Claude) |
| 5. Sender 📮 | Sends slowly, sends reminders, stops when someone replies | Gmail plus Instantly, Lemlist or Apollo |
| 6. You 🙋 | Say OK to emails, answer the "yes" replies | You! |

**The glue** that connects the rooms is a "workflow" tool like **n8n**, **Make** or **Zapier**. It's like a conveyor belt: when one room finishes, it moves the work to the next room.

**Start small:** on day 1 you can be the conveyor belt yourself (copy and paste). Add n8n or Make later, once it works.

---

## Step 1: Pick ONE kind of shop 🏪

Don't try to talk to everyone. Pick one kind, like:
- 🦷 Clinics (they answer lots of booking messages)
- 🏠 Property agents (they reply to lots of "is this house still free?" questions)
- 📦 Small online shops (they answer lots of "where is my parcel?" questions)

**Then pick ONE robot you can build for them.**
Example: *"A robot that answers clinic booking messages."*

✅ **Done when:** you can say "I help ___ with ___" in one sentence.

---

## Step 2: Make a list of shops 📝

Open **Google Sheets** (a free table on the internet).

Make these columns:
`Shop name | Website | Boss's name | Email | What they find boring | Score | Did we email?`

Find shops on:
1. **Google Maps**: type "dental clinic" and your city.
2. **LinkedIn**: look up the shop and find the boss or manager.
3. The shop's own **website**, for their email.

Find **100 shops**. Start with 20 if 100 feels like too many.

✅ **Done when:** your table has shops with names and emails.

---

## Step 3: Give each shop a score ⭐

Give 1 star for each "yes":
- ⭐ Do they do things by hand? ("WhatsApp us to book", "Email us for a price")
- ⭐ Are they hiring someone to answer messages or type data?
- ⭐ Do you know the boss's name and email?

Your email robot can help: let it read their website and write what it found.

**Email the shops with 2 or 3 stars first.**

✅ **Done when:** every shop has a score.

---

## Step 4: Get your email robot ready 🤖✉️

Like a new phone, it needs setting up before you use it.

1. **Buy a second email address name** (a "domain"), like `hello@tryyourname.com`. Don't use your main one. If something goes wrong, your main email stays safe.
2. **Let it "warm up" for 1 to 2 weeks.** Send only a few emails at first, so email companies learn you are not spam.
3. **Set the rules for your robot:**
   - 🐢 Send at most **20 to 30 emails a day**.
   - 👀 **You check the first 50 emails** before they go out.
   - ✋ When someone replies, **the robot stops** and tells you.
   - 🚪 Every email says: *"Reply 'no' and I won't email again."*

✅ **Done when:** the robot is set up and the warm-up has started.

---

## Step 5: Write the email 💌

Keep it **short**. Talk about **their** problem, not about you.

> Hi [Name],
>
> I saw [Clinic name] takes bookings by WhatsApp only. That's a lot of messages to answer every day!
>
> We build small AI helpers that answer those messages and book slots for you.
>
> Can I show you a 2-minute demo?
>
> [Your name]
>
> *Not interested? Reply "no" and I won't email again.*

If they don't reply, the robot sends a little reminder:
- 📅 **Day 3:** "Just checking you saw this 🙂"
- 📅 **Day 7:** "Here's a short video of the helper working."
- 📅 **Day 14:** "Last message from me!"

Then **stop**. Never send more than 3 reminders.

✅ **Done when:** the email and the 3 reminders are written.

---

## Step 6: When someone says "yes" 🎉

1. **Have a short call** (15 minutes) and ask:
   - "What boring job takes the most time?"
   - "Who does it now?"
   - "What apps do you use?" (WhatsApp, Gmail, Excel...)
2. **Build a small test robot** for just that one job.
3. **Let them try it** for 2 to 4 weeks.
4. **Count what changed**: "You saved 10 hours a week!"
5. **Write it down as a short success story** and show it to the next shops. 🏆

---

## Your first week (one small thing each day) 🗓️

| Day | Do this |
|---|---|
| 🟢 Day 1 | Pick one kind of shop and one robot |
| 🟢 Day 2 | Buy the second email name and start the warm-up |
| 🟢 Day 3 | Find 50 shops and put them in the table |
| 🟢 Day 4 | Find 50 more shops |
| 🟢 Day 5 | Give every shop a score and choose the best 30 |
| 🟢 Day 6 | Make a 2-minute video of your robot working and write the email |
| 🟢 Day 7 | Let the robot write 30 emails. **You check them.** Send when the warm-up is done |

---

## The 3 golden rules ✨

1. **Small steps.** One kind of shop. One robot. 20 emails a day.
2. **Be kind and honest.** Short emails, easy to say "no".
3. **You stay the boss.** The robot writes; you check.

*Want more detail? See the full plan: [sme-email-agent-plan.md](sme-email-agent-plan.md)*
