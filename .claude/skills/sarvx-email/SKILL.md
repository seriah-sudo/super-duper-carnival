---
name: sarvx-email
description: SarvX branded email system for Seriah's important outbound emails. Use whenever drafting, restyling, or updating a high-stakes email from seriah@sarvx.io — refund or dispute cases, client proposals and recaps, executive or partner outreach, offers, escalations, anything where the recipient should feel they are dealing with a real company. Applies the SarvX HTML design (wordmark header, red accent, callout boxes), the voice rules (casual, direct, kind but firm, value first, no em dashes), and the evidence-first structure. Trigger on "important email", "draft an email to", "reply to [vendor/client]", or any Gmail draft that is more than a two-line reply.
---

# SarvX Branded Email System

Every important email from Seriah goes out as a styled HTML email that reads like a
document from a real company, not a wall of text. Build it with the template in
`template.html` (same folder) and the rules below, then deliver it as a Gmail draft
with BOTH `htmlBody` (the styled version) and `body` (a faithful plaintext fallback).

## When this applies

- Disputes, refund requests, escalations (the ElliottHire case is the reference example)
- Proposals, offers, pricing, partnership outreach
- Client recaps and status updates that matter
- Any email where Seriah says "important", "make it nice", or the stakes are money or reputation

Skip it for quick one-liners, internal team pings, and casual replies. Those stay plain,
in his voice.

## Voice (non-negotiable)

- Casual, direct, simple terms. Short sentences. No corporate filler.
- Kind but firm: open with genuine credit or goodwill BEFORE any complaint or ask.
- Value first: every ask is paired with something offered (context, a solution, a session).
- **Never use em dashes.** Use periods, commas, colons, or parentheses instead.
- Numbers are concrete: dollar figures, dates, counts. No vague claims.
- Claims cite evidence inline when evidence exists: "(Exhibit 2a)", "(receipt #1234)",
  "(your July 15 email)".
- Sign-offs rotate by context: "Blessed and still building," for personal/mission emails,
  "Appreciate you," for lighter ones, plain "Thank you," for formal ones.

## Structure (adapt, do not force)

1. **Greeting + credit first.** Name what the recipient did right before anything else.
2. **Where I stand.** One paragraph of intent so the ask never reads as hostile.
3. **Attachment banner** (only if there is an attachment): gray rounded box, 📎, one line
   saying what is attached and how it maps to the email.
4. **Numbered facts.** Each numbered item is one claim with its evidence cited inline.
   Bold the load-bearing numbers and dates.
5. **Scoreboard / summary table** for the financial or outcome picture. Bordered rows,
   bold key figures.
6. **The Ask** in the red callout box. One box, one ask, exact dollar amounts or exact
   next step. Never bury the ask in a paragraph.
7. **Why it matters** paragraph in plain words. Honest, no amounts Seriah wants private.
8. **The Offer** in the slate callout box: the value-first give.
9. **Routing line + CTA**: who should handle it and the specific next step.
10. **Signature block** (red left border): name, title, phone, email link.

## Design tokens

- Accent red: `#b91c1c` (section labels, ask box border, signature bar, wordmark rule)
- Slate: `#1e293b` (offer box border, headings), text `#1f2937`, muted `#475569` / `#64748b`
- Backgrounds: page `#f4f5f7`, card `#ffffff`, ask box `#fef2f2`, offer/info box `#f8fafc`
- Borders: `#e2e8f0`, table row dividers `#eef2f7`
- Font: Arial/Helvetica only (email-safe). Body 14px/22px. Section labels 13px, bold,
  1.5px letter-spacing, uppercase, red.
- Card: 660px max width, centered, 1px border, 8px radius, on the gray page background.
- Header: "SARVX GROUP LLC" 11px bold 2.5px letter-spacing gray, then a 44px x 3px red bar.

## Technical rules (email clients are hostile)

- Inline CSS only. No `<style>` blocks, no classes, no external images, no scripts.
- Layout with `<table role="presentation">`, never divs-with-flexbox.
- Every color explicit; never rely on client defaults.
- Always provide the plaintext `body` fallback mirroring the HTML content exactly
  (structure it with CAPS section headers and "-" bullets).
- Footer line outside the card: company name + one-line context, 11px `#94a3b8`.
- Draft via the Gmail MCP (`create_draft` / `update_draft`) so Seriah reviews in Gmail.
  Sending still requires their explicit go-ahead unless they already gave it for that email.

## Reference

The canonical example is the ElliottHire refund email (thread "SarvX x ElliottHire",
Jul 2026, seriah@sarvx.io Sent folder). Match its quality bar: every claim evidenced,
credit before complaint, one red ask box, one slate offer box, zero em dashes.
