# Lewis Station Park — publishing & editing guide

Everything here assumes no coding background. Take it one section at a time.

---

## What's in the folder

```
index.html                    ← the whole website, one page
robots.txt                    ← tells Google it's allowed to list you
sitemap.xml                   ← tells Google what pages exist
images/
   planting-concept.png       ← the conceptual planting map
   share-card.png             ← the picture that shows up when someone
                                shares the link on Facebook or in a text
```

**These must stay together.** `index.html` looks for the `images` folder sitting
right next to it. If you move one without the other, the map disappears.

---

## Step 1 — Get the domain name

Buy it before you publish, so the address never has to change.

Try these, in order of preference:

- `lewisstationpark.org`
- `lewisstationstheleana.org` *(check the spelling carefully)*
- `restorelewisstation.org`

`.org` is the right suffix for a community project — it reads as civic rather
than commercial, and people trust it on a donation page.

**Where to buy:** Cloudflare Registrar or Porkbun. Both sell at cost, roughly
**$12–15/year**. Avoid GoDaddy — the first year is cheap and then the renewal
price jumps.

**Important:** buy *only* the domain. You will be offered hosting, email,
privacy protection, and site builders. Decline all of it. Privacy protection is
included free at both registrars above.

---

## Step 2 — Put the site online

Use **Netlify**. It's free for a site this size, it gives you HTTPS (the padlock)
automatically, and it does not require any coding tools.

1. Go to **app.netlify.com/drop**
2. Drag the whole site folder onto the page — the folder, not the individual files
3. It publishes in about ten seconds and gives you a temporary address like
   `random-name-12345.netlify.app`
4. Create a free account when prompted, so the site doesn't expire
5. In the site's settings, choose **Domain management → Add a domain**, enter the
   domain you bought, and follow its instructions for pointing the domain at it

Netlify's free tier covers 100 GB of traffic a month. A community park site will
use a rounding error of that.

To update the site later, drag the folder onto the same spot again. It replaces
what's there.

---

## Step 3 — Tell Google the site exists

Without this, it can take weeks to show up. With it, usually a few days.

1. Go to **search.google.com/search-console**
2. Add your domain as a property and verify it (Netlify's DNS makes this easy —
   Search Console will walk you through it)
3. Under **Sitemaps**, submit: `sitemap.xml`
4. Use **URL Inspection** on your homepage and click **Request Indexing**

Then repeat at **bing.com/webmasters** — it takes five minutes and covers Bing
plus DuckDuckGo.

---

## Step 4 — The thing that actually matters for being found

Search engines rank local pages largely on **who links to them.** For a project
like this, a handful of local links will do more than any technical tweak. Ask
each of these to link to the site:

- **City of St. Helena** — Parks & Recreation, especially their Lewis Station or
  project pages. The Commission already heard the plan in June 2026.
- **St. Helena Beautification Foundation** — Nancy Morrell is on your committee
- **Napa Valley Register** — they covered the park in 2022; a follow-up story
  with a link is worth more than everything in Step 3
- **St. Helena Chamber of Commerce** and **sthelena.com**
- **Nextdoor** and any neighborhood Facebook groups
- The **Napa Valley Community Foundation** donation page, if they'll add it

One paragraph in the Register linking to your domain will outperform months of
waiting.

---

## Editing the text yourself

Open `index.html` in a plain text editor:

- **Mac:** right-click → Open With → TextEdit. Then Format → Make Plain Text.
- **Windows:** right-click → Open With → Notepad.
- **Better option, free:** VS Code (code.visualstudio.com) — it colors the code,
  which makes it much easier to see what you're doing.

Do **not** open it in Microsoft Word. Word adds invisible formatting that breaks
the page.

### Finding what you want to change

The file has big labeled signposts in it. Search (Ctrl+F / Cmd+F) for the word
`SAVE THE DATE` and you'll land on:

```
<!-- ====================================================================
     SAVE THE DATE — *** change the volunteer day date here ***
     ==================================================================== -->
```

There's one of these above every section: ABOUT, THE TEAM, WHAT'S INCLUDED,
MAPS, SAVE THE DATE, GET UPDATES, STATUS UPDATES, IN THE NEWS, SUPPORT, SHARE.

### The one rule

Text lives *between* the angle brackets. Change that, leave the brackets alone.

```
<h3>Community Volunteer Day</h3>
   ↑            ↑              ↑
 leave      change this      leave
```

So to change the date, find `October` and type over it. Save the file. Drag the
folder back to Netlify.

### Two gotchas

- Write `&amp;` instead of `&` in your text. (It's already correct everywhere —
  just don't "fix" it.)
- Don't use curly quotes from Word. Straight quotes only.

### If something breaks

Keep a copy of the folder before you edit. If the page looks wrong, put the old
copy back. Nothing is permanent and nothing is lost.

---

## Before you go live — a short checklist

- [ ] Open the page and confirm the park photo at the top and the news thumbnail
      actually appear. They're currently pulled from `sthelena.com` and the
      Register's servers, which can break without warning. If either is blank,
      we should host our own copies.
- [ ] Test the **Donate** button end to end — confirm the money lands in the
      right fund.
- [ ] Test the email signup and the comment form (see "The two forms" below).
- [ ] Open the site on a phone.
- [ ] Once the domain is live, find and replace `lewisstationpark.org` in
      `index.html`, `robots.txt`, and `sitemap.xml` if you chose a different name.
- [ ] Paste the link into a text message to yourself and check the preview card
      looks right.

---

## The two forms (sign-ups and comments)

Both forms on the page — **Get updates** and **Share what you love about the
park** — are wired for **Netlify Forms**, which is included free with the
hosting from Step 2. They start working automatically the first time you
publish on Netlify. Nothing extra to set up, but do these two things once:

1. **Turn on email notifications** so you hear about submissions without
   checking the dashboard: in Netlify, go to **Site settings → Forms →
   Form notifications → Add notification → Email**, and enter
   `lewisstationsthelena@gmail.com`. Do it for both forms
   (`updates` and `community-voices`).
2. **Send a test through each form** from the live site and confirm the email
   arrives.

To read submissions later: Netlify dashboard → your site → **Forms**.
The free tier allows 100 submissions a month across both forms.

**Comments do not appear on the page by themselves — that's on purpose.**
You pick the ones you like and paste them into the page. In `index.html`,
search for `WHAT NEIGHBORS ARE SAYING` and follow the instructions there —
it's a copy-paste template, one small block per comment. This keeps spam and
anything inappropriate from ever showing up next to the Donate button.

---

## Swapping out images

The page has **eight** image slots. Three you can replace just by dropping a file
into the `images` folder with the exact right name — no editing at all.

| What you see | File to drop in | Best size |
|---|---|---|
| Park photo in the About section | `images/park-photo.jpg` | 1600 × 1067 (landscape) |
| News thumbnail | `images/news-photo.jpg` | 800 × 533 (landscape) |
| The conceptual planting map | `images/planting-concept.png` | 900 × 1240 (tall) |
| The share card (Facebook/texts) | `images/share-card.png` | 1200 × 630 exactly |
| Coast Live Oak card | `images/plant-live-oak.jpg` | 640 × 480 (landscape) — **done** |
| Western Redbud card | `images/plant-redbud.jpg` | 640 × 480 (landscape) |
| Ceanothus card | `images/plant-ceanothus.jpg` | 640 × 480 (landscape) |
| Arbutus card | `images/plant-arbutus.jpg` | 640 × 480 (landscape) |

**How to swap one:** name your photo exactly as shown above, put it in the
`images` folder replacing what's there, and drag the folder back to Netlify.
That's the whole process.

The slots are set up so that nothing breaks if a file isn't there. The two photo
slots fall back to the image that's there now; the four plant cards fall back to
the dashed "Photo coming soon" box. So nothing breaks while you're still gathering
photos — you can do them one at a time.

### Sizing your photos

Phone photos are usually 4000+ pixels wide, which is far bigger than a website
needs and will make the page slow to load. Shrink them first:

- **Mac:** open in Preview → Tools → Adjust Size → set width to 1600 → save
- **Windows:** open in Photos → Resize → choose the medium option
- **Either:** search "resize image" online and use any free tool

Aim for **under 300 KB per photo.** If a photo is over 1 MB, it's too big.

Use `.jpg` for photographs and `.png` for maps, diagrams, or anything with text
and flat colors.

### If you want a different name or a new photo somewhere else

Anything beyond a straight swap — adding a photo gallery, putting a picture in a
new section, changing the crop shape — is easier to just ask for. Send the photos
and say where they go.

### One important caution on the news photo

The current news thumbnail is credited **"Photo: Jesse Duarte, St. Helena Star."**
It's being loaded from the Register's own servers, which is generally how they
expect it to work. **Do not save a copy of that photo into your `images` folder** —
hosting someone else's news photo on your own site is a copyright problem, even
for a nonprofit.

Your options for that slot, in order of preference:

1. Use one of your own photos of the park
2. Ask the Star for written permission to host theirs
3. Leave it pointing at their server as it is now
4. Drop the thumbnail entirely and keep just the headline link

The park photo at the top has the same question mark — it's coming from
`sthelena.com`. Replacing it with a photo the committee took is the cleanest fix,
and it'll also load faster.
