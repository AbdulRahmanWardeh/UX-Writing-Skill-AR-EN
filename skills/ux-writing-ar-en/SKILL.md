---
name: ux-writing-ar-en
description: Extract Arabic UX copy from a screen, screenshot, or an entire Figma page, including pages with 50+ screens. Preserve names, prefer the desktop in matching breakpoint pairs, and skip copy already translated on the same Figma page. Build a separate editable 400 px English–Arabic table beside each distinct screen state with new copy. Use for bilingual UI copy audits, handoffs, or filling a supplied table component.
---

# Arabic to English UX writing

For a Figma screen, selection, or page, deliver editable bilingual tables on the design canvas. Build the table yourself when the user supplies only the source. Put English on the left and the exact Arabic source on the right. Keep one table per distinct screen or state that contributes new copy, whether the user selects one frame, two, or more.

## Identify the source screens and earlier translations

1. Work within the source Figma page. For a single screen or selection, also inspect the page for earlier screens and their handoff tables. Write only for the requested screens. For a whole page, snapshot the IDs of **all** source screens and states, including those in nested sections and outside the viewport, before creating any output. For a multi-screen selection, use the canvas order defined below. For a whole-page request or when identifying earlier screens for a single target, follow a designated flow or numbered sequence when available, then use canvas order as the fallback.
2. Inventory existing translation tables separately. Recognize a generated table by its output marker or source-frame link. A handoff can have the exact same name as its source. Use their distinct node IDs to keep them apart. Recognize older handoffs by their screen heading, paired English–Arabic cells, section rows, and placement. Use these cues together even when column labels are absent. Read only completed bilingual data rows into the lookup. Treat screen names, section headings, review chips, and any legacy language-name row as handoff metadata. Exclude handoff tables, their wrapper sections, reusable copy-table templates, and all their descendants from source extraction. A product table **inside a source screen**, such as payment history, still contributes its headings and body copy. Skip component libraries and reference boards unless the user designates them as source screens.
3. Read completed Arabic–English pairs from the identified handoffs for lookup. Associate a table with its source frame ID, or with an unambiguous screen name and location in older files. For a single screen, use its own existing rows and rows documented for earlier screens on this page. For multiple selected screens or a whole-page pass, seed the lookup with completed pairs already documented on the page. Assign each new pair to the first eligible source in processing order and skip matching occurrences on later screens. Ignore sample rows, incomplete pairs, and copy on other pages. Seeing Arabic on an earlier screen without a documented English translation does not count as a match.
4. For a page of 50 or more screens, match desktop and responsive frames across the complete snapshot and order the chosen sources before dividing them into batches. Keep that order across all batches in the request. Carry the translation lookup and the list of covered frame IDs across every batch. Recheck the destination before appending after an interruption, retain verified work, and continue from the first unfinished screen. Count a fully documented source as checked and record its paired responsive frame separately as skipped.

## Choose the source for each screen state

- Within the selection, or within the whole page for a page request, match breakpoints by **screen name, flow, and state**. For comparison only, ignore device markers such as Desktop, Responsive, Mobile, or Tablet. Read variant properties and enclosing group headings when frames have generic or identical names. Use frame dimensions and the corresponding layout to confirm the breakpoint. Keep state labels such as **Active & Filled** and **Error** in the match.
- When the same screen and state has both a desktop and a responsive frame, extract **only the desktop**, even when the responsive frame appears first. Skip all copy in that responsive frame, including mobile-only strings. Anchor the pair’s single table to the desktop. If a responsive frame is selected on its own, use it as the source.
- **Process selected screens from left to right.** After matching desktop and responsive versions, use the chosen source frames’ positions in page coordinates. Start at the leftmost frame of the top visual row and work right by increasing left-edge X. Finish that row before moving down to the next. Group slightly staggered frames by their visual row. For equal X within a row, use the top edge and then the stable frame ID. Clicking or listing the frames in a different order, layer stacking, and flow numbering do not change the order of a multi-screen selection.
- Find the working table by its source link. Use the existing desktop handoff when available. If only an earlier responsive handoff exists for the pair, reuse it beside the desktop and update its source link. Retain approved pairs supported by the desktop. Preserve previously documented responsive-only pairs in a source-linked note on that table before taking them out of the desktop rows. If both handoffs already exist, write new rows to the desktop table and flag the older responsive handoff for review.
- Build a separate set of rows for each chosen source ID. With desktop/responsive pairs for **Profile**, **Active & Filled**, and **Error**, there are three distinct sources. If these states appear on the canvas from left to right as Profile, Active & Filled, and Error, process them in that sequence. Create a separate table for each state with new copy. Share the duplicate lookup across them and keep each state’s rows separate.

## Read the screen

1. Identify the screen body using the frame hierarchy when available or the visible layout in a screenshot. Exclude the entire screen header and footer, including their titles, navigation labels, buttons, links, and legal text. Include section headings, buttons, and consent text that belong to the body, even near a screen edge. For example, capture «متابعة» inside a form and skip it inside a footer. Apply this boundary to the source screen only.
2. Use the supplied source page or frame name verbatim. For a screenshot without a supplied screen name, derive a short English heading from the body, or use “Screen 1”, “Screen 2”, and so on when the purpose is unclear. If the body has no translatable copy, record that screen as checked and continue.
3. Assemble each complete label, sentence, or paragraph in Arabic reading order **before** filtering numbers or creating rows. Keep every number that belongs to the message in that same row, including a countdown introduced by «بعد:» or a quantity such as «٧ أيام». Join inline fragments even when the number is bold, updates live, wraps to another line, or occupies its own Figma text layer.
4. After grouping, skip a numeric value that stands on its own, such as a page number or the year in a separate model-year field. Keep the independent field label. Transcribe each complete Arabic message exactly, including its spelling, punctuation, diacritics, numerals, and Latin text. Treat each independent message or control as a candidate for one row.
5. Group by the **section of the source screen**. Read the content containers or visible layout. Use a meaningful source section name, or give an unnamed region a short descriptive name such as **Categories**, **Banner**, **Services**, or **Verification form**. Use **Header** for an eligible in-body introductory section only. Keep a banner’s title, description, and button together under **Banner**. Use element roles to choose English casing, never to create groups such as **Titles** or **Buttons**. Show a section heading only when its table section contains a pair. A visible Arabic section title also gets a bilingual row when it qualifies as new copy. Preserve screen order and Arabic reading order within each section.
6. If text is cropped or illegible, keep the readable fragment and mark the gap with `⟦غير مقروء⟧` in Arabic and `⟦unreadable⟧` in English. If an entire body is missing or unreadable, identify that screen for clarification and continue through the other screens.

## Decide which rows to write

- Skip a standalone proper name, such as a person’s name in a filled profile field or a brand name shown on its own. Translate the field label «الاسم الكامل» as “Full Name”. If a name appears in a sentence, keep its original spelling, script, and capitalization in both cells and translate the surrounding words. For example, «مرحبًا، سارة» becomes “Welcome, سارة”. Apply this to names of people, companies, brands, and places. Never translate or transliterate a name.
- Compare each assembled Arabic message with the page lookup before translating. For comparison only, ignore visual line wrapping and layout whitespace. Preserve meaningful punctuation, digit forms and values, units, placeholders, and the spelling of the displayed Arabic.
- When the same Arabic, meaning, and required English wording and capitalization already have a completed pair, **skip the occurrence entirely**. Do not translate it again, copy either cell into the later table, or add a reference or placeholder row. For example, once screen 1 documents «استمرار» as “Continue”, the button contributes nothing to screen 2. If that is screen 2’s only copy, it gets no table.
- Keep a new row when context changes the translation or required capitalization. A filter chip can require “Review Needed” and a status badge “Review needed” for the same Arabic. Distinct Arabic strings keep their own rows even when their English happens to match.
- Reserve a new pair for its first occurrence so repeated controls in the same batch are recorded once. Add it to the completed lookup when both cells have been written and verified. On a retry, reuse the table for that source frame and append only missing pairs. Preserve existing editorial changes and flag conflicting approved translations that need a choice.

## Write the English

- Translate what each element does. Use a concise verb for a button, a noun phrase for a field label, and a clear statement for a message. For example, translate the button «تأكيد الدفع» as “Confirm Payment” and the toast «تم تأكيد الدفع» as “Payment confirmed”.
- For new rows, use approved product terminology and established English wording. Apply the casing for the element’s role. Keep names exactly as displayed, including a brand written in Arabic. Retain established acronym casing such as “OTP”.
- Keep each inline number in both language versions of its message. Copy the visible value exactly, including its digit script, leading zeros, separators, and signs. Translate the surrounding words. For example, «خلال ٧ أيام» becomes “Within ٧ days”, and the timer `00:59` stays `00:59`. If the user explicitly asks to document standalone values, copy those values unchanged.
- Carry over amounts, currencies, deadlines, conditions, negation, and who takes the action. Keep placeholders such as `{amount}`, `{{name}}`, and `%s` intact.
- Keep a consent statement in one row with each linked phrase in its sentence. Underline the corresponding words where supported. Add a hyperlink only when its destination is supplied.

### Apply English casing and punctuation

Choose the case from the element’s role in the source screen. Carry that casing into the bilingual handoff table. Style independently displayed controls separately, including a button inside a toast or a table cell.

- For **Title Case**, capitalize the first word and each main word. Lowercase articles, short conjunctions, and prepositions such as “a”, “an”, “the”, “and”, “or”, “at”, “by”, “for”, “in”, “of”, “on”, and “to” within a phrase. Capitalize verb particles, as in “Log In”. Use “Go to the Next Step” for a button.
- For **sentence case**, capitalize the first word of each sentence and preserve established names and acronyms. Use “Check the OTP and try again” for an error. An inline link takes the casing of its words at their position in the surrounding sentence.

| Source UI element | Use Title Case for | Use sentence case for |
| --- | --- | --- |
| Headings and supporting text | Titles | Subtitles, descriptions, body paragraphs, field hints, and other helper messages |
| Navigation and links | In-body navigation labels, tabs, breadcrumbs, step names, and standalone text links such as “View Your Request” | Links embedded in a sentence, as in “You can **view your request** here” |
| Forms and actions | Buttons and field labels, including labels for read-only fields, such as “Delivery Method” | Field and search placeholders such as “Search by city”, and ordinary dropdown, radio, checkbox, and switch options such as “Home delivery” |
| Filters, sorting, and status | Filter chips such as “Review Needed” and sort options such as “Recently Added”, including sort options in a dropdown | Status badges and tags such as “Review needed” |
| Tables in the source screen | Table headings, including column and row headings such as “Purchase Method” | Text and values in table body cells, such as “Bank transfer” |
| Feedback | Loading, success, and warning messages outside a toast or snackbar, such as “Checking Availability” or “Changes Saved” | Toast and snackbar messages, including “Changes saved”, and error messages wherever they appear |

Omit the final full stop (`.`) from every English UI string, in chat and in Figma. Keep question marks, meaningful exclamation marks, sentence separators within a paragraph, and dots inside numbers, URLs, or filenames. Transcribe the Arabic exactly, including any final period.

For a new role outside this table, follow approved casing when available. Use sentence case for new wording until the user specifies a convention for that role.

## Build the handoff in Figma

1. Create or reuse a separate table linked to each chosen source frame. Place the **first table beside the first source**, then place each subsequent table beside its own source. Use the placement rules below for single selections, multiple selections, and whole pages. An explicitly requested destination takes precedence.
2. With no template, build an editable native Auto Layout table. If the user supplies a standalone output instance, detach it in place. For a main component, create an instance of the supplied variant and detach it. For a reusable or nested template, detach a working copy outside its parent. Continue on the frame returned by `detachInstance()` when using the Plugin API. Apply the layout below to the working frame, including supplied templates. Preserve approved translations and inline links. Across multiple screens, use the supplied template to make separate working tables for each source with new copy. Apply the specified fonts, layer names, spacing, and strokes to each.
3. When explicitly asked to restyle an existing handoff, update that table in place even if all copy is already documented. Rename the wrapper and its child layers in place, move existing pairs into their source sections, and remove obsolete template rows, including **Language columns**. During ordinary extraction, treat earlier screens’ tables as lookup sources. Write only to the requested destination.

### Place each table 40 px beside its source

Use the chosen frame’s bounds in page coordinates. For a desktop/responsive pair, measure from the desktop frame. By default, put the left edge of the table **40 px to the right** of the source’s right edge and align their top edges. For a screen at `x = 100` with a width of `1440`, place its table at `x = 1580`. Use independent table frames outside the source so the UI layout stays intact.

Measure the finished 400 px table at its Hug height. Check for overlaps with source frames, responsive siblings, and other tables. If the right side is occupied, try the left with the same **40 px edge-to-edge gap**. If necessary, slide the table vertically while keeping it beside the source and maintaining the gap. If neither side has room, still create that source’s separate table in clear space below it, using a 40 px gap when possible, and report the placement exception. Keep the source designs in place. On a rerun, find the table by source ID before writing and verify its position when updating it.

### Table layout and layer names

Name the table wrapper exactly like the selected source page or screen. Copy the source name verbatim, including case, spacing, punctuation, and any device suffix. A selected frame named `Profile - Desktop` produces a table named `Profile - Desktop`. For a page containing several source screens, name each table after its own source frame. If the page itself is the single source, use its page name. Omit any handoff prefix and identify each output by its source link or ID on subsequent runs.

Use a vertical Auto Layout wrapper with a **fixed width of 400 px**, **Hug contents** height, a white background, and an empty stroke list. Give its direct child frames the exact case-sensitive names **`Screen`**, **`Section`**, and **`Row`**. Set each to **Fill container** width and **Hug contents** height. Apply Fill after adding the child to its Auto Layout parent.

| Layer name | Contents and typography |
| --- | --- |
| `Screen` | Use one horizontal header row. Put the screen name in an **Almarai Bold (700), 18 px** text layer named `Screen` on the left and the **In Progress** chip on the right. Use **Space between**, center the items vertically, and let a long title wrap within the space beside the chip. |
| `Section` | Center the visible source section name, such as **Breadcrumbs** or **Services**, in a full-width heading cell. Name the text layer `Section` and set it to **Almarai Bold, 18 px**. |
| `Row` | Use one horizontal row with two equal-width, flexible Auto Layout cells per documented pair. Use **Almarai 16 px** for both languages. Align English left in the left cell (LTR) and exact Arabic right in the right cell (RTL). Let text wrap and the taller cell determine the row height. Add rows only for new pairs. |

- **Cells.** Set each cell’s padding to **16 px left and right** and **12 px top and bottom**. Apply those insets once per cell. When a heading row doubles as its full-width cell, apply the padding directly to that frame. Keep the bilingual `Row` free of additional padding around the two padded cells.
- **Chip.** Use **Poppins SemiBold (600), 18 px** for the exact label **In Progress**. Set the chip frame to Hug contents in both axes, with **20 px left and right** and **6 px top and bottom**. Set all four corners of the chip frame to a **24 px radius** for a fully rounded pill. Use Almarai for every other text layer, including both languages and inline links.
- **Strokes.** Give every `Screen`, `Section`, and `Row` frame and every table cell its own **1 px stroke on all four sides**, with position set to **Outside** (`strokeAlign = 'OUTSIDE'`). Apply the stroke once to a heading frame that also serves as its cell. The cell edges supply the center divider. Remove standalone divider lines from a working template and keep outside strokes visible.
- **Order.** Put the first `Section` directly after `Screen`. Omit the language-name row, including any frame named `Language columns` or labeled “English / العربية”. Treat the chip as handoff metadata.

### Color bindings and verification

Use the design system’s actual variables for the table’s ordinary text, surfaces, and strokes. Identify their roles from semantic names, active mode, and similar elements. Apply the status chip’s fixed colors directly on newly built and restyled tables.

| Element | Color to apply |
| --- | --- |
| Screen name, section headings, English and Arabic text | Solid text |
| Table background and opaque row or cell surfaces | White background |
| Row and cell strokes | Light-grey line for row outlines and light-grey separator for cell outlines, or the file’s shared light-grey variable |
| **In Progress** chip frame | Solid `#2A9AAF` at 100% opacity in every mode |
| **In Progress** label | Solid white `#FFFFFF` at 100% opacity in every mode |

Replace any inherited paint style or variable on those two chip fills with the exact solid colors. For the rest of the table, resolve any missing or ambiguous variable and identify styling that is pending.

Load the Almarai styles and the Poppins SemiBold face (weight 600) available in the file before applying text. Preserve link styling when changing font families. If a required face is unavailable, report that face and keep the typography pending. Mark each output table so a later run can recognize it beside the source. Store the source page and chosen frame IDs, along with the matched responsive frame IDs, in persistent node metadata where available. Otherwise retain an explicit source link on the output.

Re-read the actual frame and text properties. Match the wrapper name to its source and check the case of `Screen`, `Section`, and `Row`. Verify the 400 px width, Fill/Hug settings, fonts and sizes, cell and chip padding, and 1 px Outside strokes on each row and cell. Verify that the screen name uses Almarai Bold (700) and all four chip corners are 24 px. Check the chip’s label, weight, right alignment, and actual fill values of `#2A9AAF` and `#FFFFFF`. Verify that the first `Section` follows `Screen` directly and long text wraps in either language. Trace each pair to its source section and check its casing, punctuation, and inline numbers. Check names against the original and verify the 40 px gap for each new table. Reconcile desktop sources, skipped responsive counterparts, and screens with no new rows against the initial inventory.

List table links in the same order the source screens were processed. Give each link its source name, or identify the page and frame when a link is unavailable. Report screens checked, responsive counterparts skipped, new rows written, repeated occurrences skipped, and any unresolved work. For a screenshot without a destination, prepare the pairs and ask for the editable Figma page. Confirm a canvas handoff only after verifying it there.

## Text output when requested

For an explicit chat preview or export, use the same desktop selection, name handling, source sections, and duplicate-skipping rules. Format a separate table for each distinct source with new copy. In Markdown, put the bold screen name and its status above the table. Use the first real section name as the Markdown table header. Put subsequent section names in bold in the first cell of their own row. Omit language labels. In an HTML export, mirror the typography, fixed chip colors and corner radius, padding, and row and cell outlines from the Figma table. Use two equal columns, centered spanning section headings, and a borderless table wrapper. Set the table to `dir="ltr"` and each Arabic cell to `lang="ar" dir="rtl"`.

### Verify Mobile Number · In Progress

| **Verification form** | |
| :--- | ---: |
| Enter the Verification Code | أدخل رمز التحقق |
| Verification Code | رمز التحقق |
| We sent a code to your mobile number | أرسلنا رمزًا إلى رقم جوالك. |
| Didn’t receive the verification code? Request a new code in 00:59 | لم يصلك رمز التحقق؟ اطلب رمز جديد بعد: 00:59 |
| Resend Code | إعادة إرسال الرمز |
