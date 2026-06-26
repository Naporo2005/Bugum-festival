# The Fire Festival (Bugum Chugu) — Heritage Website

A single self-contained HTML page: history, timeline, video showcase, photo gallery, cultural info, and a community contribution form with live previews. No build step — open the file or upload it anywhere that serves HTML.

## File

`fire-festival-heritage.html` — everything (HTML, CSS, JS) is in this one file. There's no separate editor panel or JS wiring file for this one, unlike the other Yomyom templates — it's a single static page, not a client-editable template.

## What's in each section

1. **Hero** — full-height intro with a drifting ember-glow background animation.
2. **Festival Story** — the lost-prince legend, two-column layout.
3. **Timeline** — vertical timeline with a glowing dot that tracks down the spine as you scroll.
4. **Video Showcase** — click a card to open a fullscreen video modal. Closes on the × button, clicking outside, or ESC.
5. **Gallery** — currently commented out in your copy. The lightbox code (open image, next/prev, swipe, ESC) is still there and ready if you uncomment the section.
6. **Cultural Importance** — five info cards (Unity, Heritage, Community, Tradition, Cultural Identity).
7. **Community Contributions** — name/town/message form plus drag-and-drop image and video upload with thumbnail previews and a remove (×) button per file.
8. **Community Stories** — story cards with like buttons. New submissions from the form above get added here live.
9. **Festival Statistics** — four stat counters that animate when scrolled into view.
10. **Call to Action** — final push toward the contribution form.
11. **Footer** — nav links, social icons, contact (currently set to your email/phone/WhatsApp).

## Swapping in real media

Search for these and replace with your own files or URLs:

- `<img>` `src` attributes — hero background, story illustration, video thumbnails.
- `data-video-src` on each `.video-card` — currently pointing at your local filenames (`Fire1.mp4`, etc). Drop your actual video files next to the HTML file with matching names, or change the attribute to match your filenames.
- If you uncomment the Gallery section, do the same for each `data-full` (full-size image shown in the lightbox) and the `<img src>` (thumbnail).

## Things to know before it goes live

- **Preloader**: a flame icon with "Lighting the torch" shows briefly while the page loads, then fades out. If you ever swap the hero image for a large video, you may want to bump the safety timeout in the script (`setTimeout(hideLoader, 4000)`) a bit higher so it doesn't cut off before the video is ready.
- **Form submissions aren't saved anywhere yet.** Right now, submitting the form just adds the story to the page for that visit — it disappears on refresh and nothing is sent anywhere. To make it permanent, wire it up the same way as your other editors: a Supabase insert for the story/images/videos plus an EmailJS notification, following the same plain-fetch pattern as `realestate-supabase.js`. Happy to build that out when you're ready — it would need your Supabase project URL/key and table structure.
- **Stats are hardcoded** (120+ years, 40+ communities, 2,400+ photos, 650+ stories) — not pulling from anything live. Update the `data-count` numbers directly in the HTML, or connect them to Supabase later once submissions are actually being stored.

## Browser support

Plain HTML/CSS/JS, no frameworks. Works in any modern browser. Respects "reduce motion" accessibility settings (animations turn off automatically for users who have that set).
