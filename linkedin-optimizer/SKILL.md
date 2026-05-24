---
name: linkedin-optimizer
description: Complete LinkedIn profile optimization — headline, about, experience, skills, and keyword injection. Walks you through rewriting each section with industry-specific keywords, then updates your profile directly via Chrome browser automation. Works for any industry or career goal. Use this skill whenever the user mentions LinkedIn profile optimization, improving their LinkedIn, rewriting their headline or about section, LinkedIn SEO, LinkedIn keyword strategy, making their LinkedIn more discoverable, updating their LinkedIn for a career change, or anything related to overhauling or polishing a LinkedIn profile — even if they just say "fix my LinkedIn" or "make my LinkedIn better." Also trigger when the user wants help attracting clients, recruiters, or partners through LinkedIn positioning.
---

# LinkedIn Profile Optimizer

A step-by-step workflow for overhauling a LinkedIn profile — headline, about, experience, skills, and keyword injection — using Chrome browser automation on the user's actual LinkedIn page.

This skill works for **any industry or career goal**: photographers, consultants, engineers, lawyers, founders, freelancers, executives, creatives, and everyone in between. The process adapts based on what the user is trying to attract (clients, jobs, partnerships, speaking gigs, collaborations).

## Prerequisites

- The user must be logged into LinkedIn in Chrome
- Chrome MCP (`mcp__Claude_in_Chrome__*`) must be connected
- The user should have their LinkedIn profile open, or be ready to navigate to it

## Important Principles

These principles apply throughout every step of the workflow. Internalize them before starting.

**Always get approval before saving.** Never update any section of the user's LinkedIn without showing them the proposed copy first and getting explicit confirmation. This is their professional identity — treat every edit as consequential.

**Frame copy for the user's actual goal.** The biggest mistake is defaulting to recruiter/ATS language when the user is a business owner trying to attract clients. Ask about their goal early, and let that answer shape every word choice. A photographer's experience section reads very differently from a software engineer's.

**Write like a human, not a keyword machine.** LinkedIn SEO matters, but readability matters more. The goal is to weave high-value search terms into copy that sounds natural and compelling. If a sentence feels stuffed, rewrite it until it flows. A profile that reads well and ranks well is the target.

**Respect character limits.**
- Headline: 220 characters max
- About: 2,600 characters max (aim for ~250 words)
- Experience descriptions: 2,000 characters each

**Be inclusive.** Don't assume gender, relationship status, or personal details. Use neutral language throughout.

**Never use the word "luxury"** unless the user specifically requests it. It's overused and often signals inauthenticity. Find more specific, compelling ways to describe premium positioning.

**Handle LinkedIn's UI quirks.** LinkedIn frequently shows connection suggestion popups, "Add profile section" modals, and notification overlays. Dismiss these by clicking "Skip," "No thanks," or the X button before proceeding with edits. When replacing text in a field, use Cmd+A (Mac) or Ctrl+A (Windows) to select all existing content before typing the replacement.

---

## Workflow

### Phase 1: Read the Current Profile

Navigate to the user's LinkedIn profile and capture its current state.

1. Use Chrome MCP to navigate to `https://www.linkedin.com/in/me/` (this redirects to the logged-in user's profile)
2. Take a screenshot of the profile hero area (photo, headline, location)
3. Scroll down and screenshot the About section
4. Scroll down and screenshot the Experience section
5. Scroll down and screenshot the Skills section
6. Use `read_page` and `get_page_text` to extract the text content of each section

Save the extracted text so you can reference it throughout the optimization. Present a brief summary to the user: "Here's what I see on your current profile..." covering their current headline, about summary (or lack thereof), number of experience entries, and number of skills listed.

### Phase 2: Discovery Interview

Before rewriting anything, gather the context needed to write effective copy. Use the AskUserQuestion tool (or ask in chat) to get answers to these questions:

1. **Industry and role**: "What's your primary industry and role? (e.g., wedding photographer, fractional CFO, UX designer, real estate agent)"

2. **Goal**: "What are you trying to attract through LinkedIn? Pick all that apply:"
   - Clients / customers
   - Job offers
   - Business partnerships
   - Speaking or media opportunities
   - Collaborations with peers
   - General professional visibility

3. **Positioning guardrails**: "Are there any words, phrases, or positioning you want to avoid? For example, some people don't want to be called a 'freelancer' or 'guru.'"

4. **Credentials and proof points**: "Do you have any of the following to highlight?"
   - Press features or media mentions
   - Awards or honors
   - Certifications or licenses
   - Notable clients or brands (that you can publicly name)
   - Publications, books, or speaking credits
   - Years of experience worth calling out

5. **Markets and locations**: "Do you serve specific geographic markets or locations? (e.g., 'NYC and the Tri-State area,' 'nationwide,' 'remote clients globally')"

6. **Differentiator**: "In one sentence, what makes you different from others who do what you do?"

These answers drive every section rewrite. Reference them constantly.

### Phase 3: Rewrite the Headline

The headline is the single most important field for LinkedIn search visibility. It appears in search results, connection requests, comments, and messages.

**Research step:** Before writing options, think about what search terms someone looking for this user's services (or someone like them) would type into LinkedIn. These exact-match phrases should appear in the headline.

**Generate 3-5 headline options** following these principles:
- Lead with the primary role or title using the exact words a searcher would use
- Use pipe separators (`|`) or bullet separators (`·`) to pack in multiple keywords
- Include geographic markets if relevant
- Include top credential or differentiator if space allows
- Stay under 220 characters
- For business owners: lead with what clients search for, not internal titles
- For job seekers: lead with target role title, then key skills

**Example patterns** (adapt to user's industry):
```
[Primary Role] | [Market/Location] | [Credential] | [Differentiator]
[Target Role] · [Key Skill 1] · [Key Skill 2] · [Industry Focus]
[What You Do] for [Who You Serve] | [Location] | [Credential]
```

Present all options to the user with character counts. Let them pick one, mix and match, or request modifications. Only after they confirm, update the headline:

1. Navigate to the profile edit view (click the pencil/edit icon near the headline)
2. Find the headline input field
3. Select all existing text (Cmd+A / Ctrl+A) and type the new headline
4. Save changes

### Phase 4: Rewrite the About Section

The About section is a 2,600-character canvas for keyword-rich storytelling. It needs to serve both LinkedIn's search algorithm and the human reader.

**Structure the About section like this:**

1. **Opening hook (1-2 sentences):** State what you do, who you do it for, and where — using exact-match search phrases. This is the most important paragraph for SEO because LinkedIn weights the opening.

2. **Proof and credibility (2-3 sentences):** Weave in press features, awards, certifications, years of experience, or notable clients. Don't just list them — contextualize them. "Featured in [Publication]" is fine; "As seen in [Publication] for work on [notable project]" is better.

3. **Approach or differentiator (2-3 sentences):** What makes their work or approach distinctive? This is where personality comes through. Avoid generic phrases like "passionate professional" — be specific about what they actually do differently.

4. **Markets and scope (1-2 sentences):** Where they operate, who they serve, what types of projects or roles they take on. Use location names that people search for.

5. **Call to action + contact info (1-2 sentences):** Tell the reader what to do next. Include email if the user wants it. Keep it direct: "Get in touch at [email]" or "Let's connect — message me here or email [address]."

**Writing guidelines:**
- Aim for ~250 words (well under the 2,600 char limit for readability)
- Write in first person ("I") — it's more personal and LinkedIn-native
- Front-load keywords in the first two sentences
- Use line breaks between paragraphs for readability (LinkedIn doesn't render markdown)
- Don't use hashtags in the About section — they look spammy
- Don't use bullet points — write in flowing prose
- Include industry-specific search terms naturally throughout

Draft the About section and present it to the user for review. Show the character count. Revise based on their feedback until they approve.

To update on LinkedIn:
1. Scroll to the About section and click the pencil/edit icon
2. Select all existing text in the About field (Cmd+A / Ctrl+A)
3. Type (or paste) the approved About text
4. Save changes

### Phase 5: Rewrite Experience Descriptions

Each experience entry is an opportunity to add searchable keywords and demonstrate impact.

**For each role listed on the profile:**

1. Read the current description (if any)
2. Determine if it needs a rewrite, enhancement, or is fine as-is
3. If the entry has no description at all, write one
4. If the entry is a duplicate or orphaned (empty role with no dates or description), flag it for the user and ask if they want to delete it

**Writing guidelines for experience descriptions:**

- **For business owners / client-attractors:** Frame descriptions around what you deliver to clients, the types of projects you take on, and the markets you serve. Avoid corporate-speak. Think "what would make a potential client say 'that's exactly what I need'?"

- **For job seekers:** Frame descriptions around impact, metrics, and transferable skills. Use the language of job postings in your target role. Think "what would make a hiring manager's eyes light up?"

- **For partnership / speaking / visibility seekers:** Frame descriptions around reach, expertise, and thought leadership. Highlight collaborations, audiences reached, and domains of expertise.

Keep each description under 2,000 characters. Use short paragraphs, not walls of text.

Present all proposed experience rewrites to the user at once (so they can see the full picture) before making any changes. After approval, update each one:

1. Click the pencil/edit icon on the experience entry
2. Find the description field
3. Select all and replace with the new text
4. Save changes
5. Repeat for each entry

If the user confirms they want to delete orphaned/duplicate entries:
1. Click the three-dot menu or edit icon on the entry
2. Click "Delete experience" (or equivalent)
3. Confirm the deletion

### Phase 6: Keyword Injection Pass

After all sections are updated, do a final review for search optimization.

1. Research 10-15 high-value search terms for the user's industry that people actually type into LinkedIn when looking for someone like them
2. Compare these terms against the completed profile text (headline + about + experience)
3. Identify which valuable terms are missing
4. For each missing term, find a natural place to weave it into the About or Experience sections — add it in a way that enhances (not clutters) the existing copy
5. Present the proposed additions to the user: "I'd like to add these search terms to strengthen your discoverability: [list]. Here's where I'd place each one: [show context]."
6. After approval, make the edits on LinkedIn

The goal is 5-8 additional keyword placements, not 20. Quality over quantity.

### Phase 7: Add or Update Skills

LinkedIn's Skills section is a direct ranking signal. Having relevant skills listed (and associated with experience entries) improves search placement.

1. Navigate to the Skills section of the profile
2. Check what skills are currently listed
3. Based on the user's industry and goals, suggest 5-10 skills to add (if the section is thin) or swap (if existing skills are off-target)
4. Present the suggestions: "Here are the skills I'd recommend adding to boost your discoverability for [their goal]. I've matched each to the experience entry it relates to."
5. After approval, add each skill:
   - Click "Add a new skill" (or the + button in the Skills section)
   - Type the skill name
   - Associate it with the relevant experience entry when prompted
   - Save

### Phase 8: Final Review

Wrap up with a comprehensive before/after summary.

1. Navigate back to the top of the profile
2. Take a full screenshot of the updated profile (hero area, headline)
3. Scroll and screenshot the updated About section
4. Scroll and screenshot the updated Experience section

Present a summary to the user covering:
- **Headline**: before vs. after (with character counts)
- **About**: brief description of what changed and key keywords added
- **Experience**: which entries were rewritten, added, or deleted
- **Skills**: which skills were added
- **Keywords**: list of search terms now present in the profile that weren't before

Close with practical next steps the user can take on their own:
- Ask for skill endorsements from colleagues
- Request recommendations from clients or managers
- Update their profile photo and banner if outdated
- Turn on "Open to Work" or "Providing Services" if relevant
- Share a post to signal the profile refresh to their network

---

## LinkedIn Navigation Reference

These are common UI patterns you'll encounter. Adapt as needed — LinkedIn updates its interface frequently.

**Editing the headline / intro:**
- Click the pencil icon in the profile intro/hero section
- The headline field is in the edit modal that opens
- Save button is at the bottom of the modal

**Editing the About section:**
- Scroll to the About section
- Click the pencil icon (top-right of the section)
- Edit in the text area that appears
- Click Save

**Editing Experience:**
- Scroll to the Experience section
- Click the pencil icon on the specific entry
- Edit the description field
- Click Save

**Adding Skills:**
- Scroll to the Skills section
- Click "Add a new skill" or the + icon
- Type the skill name in the search field
- Select from suggestions
- Associate with an experience entry
- Click Save/Add

**Dismissing popups:**
- Connection suggestions: click "Skip" or X
- "Add to your profile" prompts: click "Skip for now"
- Notification overlays: click X or dismiss
- "People also viewed" sidebar: ignore (doesn't block editing)

---

## Troubleshooting

**LinkedIn shows a login wall or CAPTCHA:** Ask the user to log in manually, then resume.

**Edit modal won't open:** Try refreshing the page first. LinkedIn sometimes loads in a partial state. Take a screenshot, identify the exact edit button, and try again.

**Character count exceeded:** If the user's approved text is over the limit, trim from the least keyword-dense area and re-present for approval.

**Skills section not visible:** Some profiles have the Skills section collapsed or hidden. Scroll further down or click "Show all sections" if available.

**Changes don't appear to save:** After clicking Save, wait 2-3 seconds and take a screenshot to verify. If changes didn't stick, try the edit again. LinkedIn occasionally has save lag.
