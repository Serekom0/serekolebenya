# Before you publish

Two things need real values. Both live at the top of the `<script>` block in
`index.html`, under `CONFIGURATION`.

**1. The Story Letter.** Create a list at buttondown.com (free tier is fine;
Kit and MailerLite work the same way), then replace `YOUR-USERNAME`:

```js
newsletter: 'https://buttondown.com/api/emails/embed-subscribe/sereko'
```

**2. The contact form.** Create a form at formspree.io, then replace
`YOUR-FORM-ID` with the endpoint it gives you:

```js
contact: 'https://formspree.io/f/abcd1234'
```

Until those are replaced, both forms tell the visitor plainly that they aren't
connected yet. They do not pretend a message was sent. Test each one after you
swap the values in.

Also worth doing before launch:

- Replace `https://sereko-lebenya.example/` in the `canonical` and `og:image`
  tags with your real domain.
- Add an `og-card.jpg` (1200×630) to `assets/images/` — this is the picture
  that appears when someone shares the site.
- The **Find this book** button on the Books page still points at `#`. Give it
  a retailer link, or change it to something honest until the book is buyable.
- The **Media** page lists three items with no outlet, date, or link. If those
  conversations haven't happened yet, take the page down until they have.
- Location now reads **East Midlands, England** throughout.
- You're collecting email addresses in the UK, so the "Privacy" link in the
  footer needs to go to a real privacy notice, not the contact form.

# What changed in this pass

- Removed 11,684 characters of leftover third-party editor script.
- Forms now send real data (and say so honestly when they can't).
  Added `name` attributes to the contact fields — without them, nothing would
  have been submitted even once the endpoint was live.
- Every page and every essay now has its own URL (`#/books`,
  `#/essays/the-season-nobody-sees`). Back button, bookmarks and sharing work,
  and each one sets its own page title and description.
- Essay cards are real links instead of clickable `<article>` elements, so
  they're keyboard- and screen-reader-navigable, and can be opened in a new tab.
- Fixed three invalid nested `<p>` blocks that were silently killing the
  `.prose` styling on Media, Speaking and Contact.
- Fixed the pillar filters (the active state never updated) and removed a dead
  `.stories-page` selector.
- Removed the duplicate `@import` — fonts were being requested twice.
- Deleted three unused images; recompressed the book cover from 736 KB to
  187 KB.
- Added a skip link, a `<main>` landmark, `aria-current` on the active nav
  item, visible focus rings, live regions on the forms, Escape-to-close and
  focus return on the mobile menu.
- Theme choice now persists between visits.
- Added favicon, canonical, Open Graph image, Twitter card, and Person
  structured data.

Total page weight is down from 1.2 MB to about 400 KB.
