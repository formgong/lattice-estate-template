# Lattice Estate — luxury home builder site with a Formgong form

**Live demo:** https://estate.formgong.com · Download: the [latest release](https://github.com/formgong/lattice-estate-template/releases/latest) zip.

[![Deploy to Cloudflare](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/formgong/lattice-estate-template) [![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fformgong%2Flattice-estate-template&project-name=lattice-estate&repository-name=lattice-estate)

Each button copies the site to your GitHub and publishes it. Then replace `fk_your_access_key` in `index.html` of your copy with your Formgong access key (free at https://formgong.com/new) and commit: the host republishes on its own.

Шаблон сайту будівельника люкс-будинків з формою Formgong

A variation of [Lattice](https://github.com/formgong/lattice-template). It keeps the core: every border sits on a grid line, the frames draw from a corner, and the boxes slide in. On top of that, the page tells one build backwards. Scrolling rewinds a finished cliffside villa to the shell under construction, then to the bare concrete frame, then to the first drawing. The page ends on the team around a table with a consultation form.

## English

**Set up the form**

1. Create a form in the Formgong dashboard and copy its access key.
2. In `index.html`, replace `fk_your_access_key` with that key.
3. Optional: put your Turnstile site key in `data-sitekey` on `<form id="fg-form">`.

The form sends `name`, `email`, `phone` (optional), `budget` and `message`. It shows "received" only when the server answers `success: true`.

**Story**

- `img/built.webp`, `shell.webp`, `frame.webp` and `drawing.webp` must show the same house from the same camera position. Each stage hides the one before it: the build and the frame wipe in from the right behind a brass line, and the drawing opens as a circle from one point.
- On the drawing stage the grid becomes stronger, like drafting paper. The script then draws dimension lines with A/B axis bubbles along grid lines.
- Captions and timeline labels are in the `STAGES` array in the script.
- With `prefers-reduced-motion: reduce`, the stages switch without wipes.

**Images.** All five were made for this template with FLUX.2 [klein] 4B (Apache 2.0) on Cloudflare Workers AI, within the free daily allowance.
- The finished villa and the team are text-to-image.
- The build stage is an edit of the villa, guided by a line drawing traced from it. The frame stage is an edit of an earlier build stage.
- Both stages are locked to the villa photo. Outside the house they are the photo pixel for pixel, so sky, sea and cliff never move. The roof and the middle slab are the photo's own slabs, re-toned to raw concrete, so the edges line up across the wipe.
- The drawing is traced from the villa photo.

## Українська

Варіація Lattice для будівельника вілл. Під час прокрутки готовий будинок «перемотується» назад: коробка під дахом, бетонний каркас, перше креслення. Сторінка закінчується командою за столом і формою консультації з полем бюджету.

**Форма:** замініть `fk_your_access_key` на ключ форми з кабінету Formgong. Форма надсилає ім'я, пошту, телефон, бюджет і повідомлення.

**Картинки:** усі п'ять зроблено моделлю FLUX.2 [klein] 4B (ліцензія Apache 2.0) у Cloudflare Workers AI, у межах безкоштовної денної норми. Поза будинком етапи стройки піксель у піксель збігаються з фото. Дах і середня плита взяті з самого фото й перефарбовані під сирий бетон, тож краї збігаються через «шторку». Креслення обведене з фото.
