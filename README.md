# Lattice Estate — luxury home builder site with a Formgong form

**Live demo:** https://estate.formgong.com · Download: the [latest release](https://github.com/formgong/lattice-estate-template/releases/latest) zip.

> **License:** code under MIT. `img/shell.webp` and `img/frame.webp` were generated with FLUX.2 [klein] 9B, whose weights are under the FLUX Non-Commercial License; check the FLUX terms (https://bfl.ai/legal/terms-of-service) before commercial use, or replace them. The other three images (FLUX.2 [klein] 4B, Apache 2.0, and a drawing traced from one of them) carry no such restriction.

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

**Images.** All five were made for this template on Cloudflare Workers AI, within the free daily allowance. The finished villa and the team are text-to-image with FLUX.2 [klein] 4B. The build and frame stages are FLUX.2 [klein] 9B edits of the villa. Each one was aligned with a straight-line-safe perspective warp and then locked to the villa photo: outside the house the stages are the photo pixel for pixel, so sky, sea and cliff never move, and the roof and slabs land within 1.5 px. The drawing is traced from the villa photo itself, so it matches by construction. Check the model terms at https://bfl.ai/legal/terms-of-service before you sell the images as part of a template.

## Українська

Варіація Lattice для будівельника вілл. Під час прокрутки готовий будинок «перемотується» назад: коробка під дахом, бетонний каркас, перше креслення. Сторінка закінчується командою за столом і формою консультації з полем бюджету.

**Форма:** замініть `fk_your_access_key` на ключ форми з кабінету Formgong. Форма надсилає ім'я, пошту, телефон, бюджет і повідомлення.

**Картинки:** усі зроблено в Cloudflare Workers AI, у межах безкоштовної денної норми. Етапи стройки — це редагування фото вілли. Поза будинком вони піксель у піксель збігаються з фото, тож небо, море й скеля не рухаються, а дах і плити зсунуті не більше ніж на 1,5 px. Креслення обведене прямо з фото. Якщо ставите свій будинок, знімайте всі етапи з однієї точки.
