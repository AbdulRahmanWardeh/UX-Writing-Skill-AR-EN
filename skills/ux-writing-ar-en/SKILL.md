---
name: ux-writing-ar-en
description: Extract Arabic UX copy from a screen, screenshot, or an entire Figma page, including pages with 50+ screens. Skip copy already translated on the same Figma page and build editable 400 px English–Arabic handoff tables grouped by source section, using the file’s color variables. Use for bilingual UI copy audits, handoffs, or filling a supplied table component.
---

# Arabic to English UX writing

For a Figma screen, selection, or page, deliver editable bilingual tables on the design canvas. Build the table yourself when the user supplies only the source. Put English on the left and the exact Arabic source on the right. A screen gets a new table only when it contributes new copy.

## Identify the source screens and earlier translations

1. Work within the source Figma page. For a single screen or selection, also inspect the page for earlier screens and their handoff tables. Write only for the requested screens. For a whole page, snapshot the IDs of **all** source screens and states, including those in nested sections and outside the viewport, before creating any output. Follow the user’s flow or numbered screen order when available. Otherwise use canvas reading order, top to bottom and right to left within a row, with a stable frame ID as a tie-breaker.
2. Inventory existing translation tables separately. Recognize a generated table by its output marker or source-frame link. Recognize older handoffs by their screen heading, paired English–Arabic cells, section rows, and placement. Use these cues together even when column labels are absent. Read only completed bilingual data rows into the lookup. Treat screen names, section headings, review chips, and any legacy language-name row as handoff metadata. Exclude handoff tables, their wrapper sections, reusable copy-table templates, and all their descendants from source extraction. A product table **inside a source screen**, such as payment history, still contributes its headings and body copy. Skip component libraries and reference boards unless the user designates them as source screens.
3. Read completed Arabic–English pairs from the identified handoffs for lookup. Associate a table with its source frame ID, or with an unambiguous screen name and location in older files. For a single screen, use its own existing rows and rows documented for earlier screens on this page. For a whole-page pass, seed the lookup with completed rows already present on the page and give each new string to its first eligible screen in flow order. Ignore sample rows, incomplete pairs, and copy on other pages. Seeing Arabic on an earlier screen without a documented English translation does not count as a match.
4. For a page of 50 or more screens, process the complete snapshot in manageable batches within the same request. Carry the translation lookup and the list of covered frame IDs across every batch. Recheck the destination before appending after an interruption, retain verified work, and continue from the first unfinished screen. Count a duplicate-only screen as covered.

## Read the screen

1. Identify the screen body using the frame hierarchy when available or the visible layout in a screenshot. Exclude the entire screen header and footer, including their titles, navigation labels, buttons, links, and legal text. Include section headings, buttons, and consent text that belong to the body, even near a screen edge. For example, capture «متابعة» inside a form and skip it inside a footer. Apply this boundary to the source screen only.
2. Use the supplied screen or frame name, or derive a short English heading from the body. Use “Screen 1”, “Screen 2”, and so on if the purpose is unclear. If the body has no translatable copy, record that screen as checked and continue.
3. Assemble each complete label, sentence, or paragraph in Arabic reading order **before** filtering numbers or creating rows. Keep every number that belongs to the message in that same row, including a countdown introduced by «بعد:» or a quantity such as «٧ أيام». Join inline fragments even when the number is bold, updates live, wraps to another line, or occupies its own Figma text layer.
4. After grouping, skip a numeric value that stands on its own, such as a page number or the year in a separate model-year field. Keep the independent field label. Transcribe each complete Arabic message exactly, including its spelling, punctuation, diacritics, numerals, and Latin text. Treat each independent message or control as a candidate for one row.
5. Group by the **section of the source screen**. Read the content containers or visible layout. Use a meaningful source section name, or give an unnamed region a short descriptive name such as **Categories**, **Banner**, **Services**, or **Verification form**. Use **Header** for an eligible in-body introductory section only. Keep a banner’s title, description, and button together under **Banner**. Use element roles to choose English casing, never to create groups such as **Titles** or **Buttons**. Show a section heading only when its table section contains a pair. A visible Arabic section title also gets a bilingual row when it qualifies as new copy. Preserve screen order and Arabic reading order within each section.
6. If text is cropped or illegible, keep the readable fragment and mark the gap with `⟦غير مقروء⟧` in Arabic and `⟦unreadable⟧` in English. If an entire body is missing or unreadable, identify that screen for clarification and continue through the other screens.

## Decide which rows to write

- Compare each assembled Arabic message with the page lookup before translating. For comparison only, ignore visual line wrapping and layout whitespace. Preserve meaningful punctuation, digit forms and values, units, placeholders, and the spelling of the displayed Arabic.
- When the same Arabic, meaning, and required English wording and capitalization already have a completed pair, **skip the occurrence entirely**. Do not translate it again, copy either cell into the later table, or add a reference or placeholder row. For example, once screen 1 documents «استمرار» as “Continue”, the button contributes nothing to screen 2. If that is screen 2’s only copy, it gets no table.
- Keep a new row when context changes the translation or required capitalization. A filter chip can require “Review Needed” and a status badge “Review needed” for the same Arabic. Distinct Arabic strings keep their own rows even when their English happens to match.
- Reserve a new pair for its first occurrence so repeated controls in the same batch are recorded once. Add it to the completed lookup when both cells have been written and verified. On a retry, reuse the table for that source frame and append only missing pairs. Preserve existing editorial changes and flag conflicting approved translations that need a choice.

## Write the English

- Translate what each element does. Use a concise verb for a button, a noun phrase for a field label, and a clear statement for a message. For example, translate the button «تأكيد الدفع» as “Confirm Payment” and the toast «تم تأكيد الدفع» as “Payment confirmed”.
- For new rows, use approved product terminology and established English wording. Apply the casing for the element’s role. Preserve the official spelling of brands, proper names, and acronyms in either case, including “Shop by Motory”, “Apple Pay”, and “OTP”.
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

1. Use the requested destination. Otherwise place a single table in clear space beside its screen. For a page, arrange the tables in source order in a dedicated **UX Copy — EN / AR** section in unused space on that page. Reuse the section and any table associated with the target frame.
2. With no template, build an editable native Auto Layout table. If the user supplies a standalone output instance, detach it in place. For a main component, create an instance of the supplied variant and detach it. For a reusable or nested template, detach a working copy outside its parent. Continue on the frame returned by `detachInstance()` when using the Plugin API. Apply the layout below to the working frame, including supplied templates. Preserve compatible font families, weights, spacing, inline links, and approved translations.
3. When explicitly asked to restyle an existing handoff, update that table in place even if all copy is already documented. Move its existing pairs into their source sections and remove obsolete template rows, including **Language columns**. During ordinary extraction, treat earlier screens’ tables as lookup sources. Write only to the requested destination.

### Table layout and layer names

Make the table wrapper a vertical Auto Layout frame with a **fixed width of 400 px**, **Hug contents** height, a white background, and **no stroke**. Name the wrapper **UX Copy — <screen name>** so the table is identifiable on the page.

Use the following exact lowercase names for its direct child frames. Set **every** `screen`, `section`, and `row` to **Fill container** width and **Hug contents** height. When using the Plugin API, append each Auto Layout child to its parent before setting `layoutSizingHorizontal = 'FILL'` and `layoutSizingVertical = 'HUG'`.

| Layer name | What to put in it |
| --- | --- |
| `screen` | One horizontal heading row. Put the visible screen name, such as **Home**, on the left. Name its text layer `screen` and set it to **18 px**. On the right place a blue pill labeled exactly **In Progress** at **16 px**. Use a horizontal **Space between** layout (`primaryAxisAlignItems = 'SPACE_BETWEEN'`) and vertically center both items. Let the chip hug its label and let a long screen name wrap within the available width. |
| `section` | One full-width, centered, bold **16 px** heading per source section with copy. Name the heading text layer `section` and show the actual section name, such as **Categories**, **Banner**, or **Services**. |
| `row` | One horizontal row per documented translation pair. Add rows only for new pairs. Use two equal flexible cells with English on the left, LTR and left-aligned, and exact Arabic on the right, RTL and right-aligned. Set both texts to **16 px** and let them wrap so the taller cell determines the row height. |

Use **16 px for every text layer except the 18 px screen name**, including the chip label. Put the first content section directly after the `screen` row. Omit the entire language-name row, including any frame named `Language columns` or labeled “English / العربية”. The blue chip belongs to the handoff and contributes no translation row.

Keep **1 px borders on the row frames** and a single light-grey vertical separator between the cells of each bilingual `row`. Draw each shared edge once. The screen and section headings span the full width with no center divider. Leave the table wrapper’s stroke empty.

### Color bindings and verification

Resolve the design system’s actual color variables once per page. Use semantic names, active mode, and bindings on matching elements in the file. Bind each fill or stroke, including those inherited from a template.

| Element | File variable to bind |
| --- | --- |
| Screen name, section headings, English and Arabic text | Solid text |
| Table background and opaque row or cell surfaces | White background |
| Row borders and cell separators | Light-grey line for borders and light-grey separator for dividers, or their shared variable |
| **In Progress** chip | The file’s blue status, informational, or brand-blue chip background. Bind the label to the corresponding foreground variable used by that chip style |

If the file has a blue status chip, use its bindings in the active mode. Resolve missing or ambiguous variables with the user and mark that styling as pending. A matching literal color does not establish a binding.

Load the required fonts before setting text. Mark the output section and tables so a later run can recognize them. Store the source page and frame IDs on each table in persistent node metadata where available. Otherwise retain an explicit source-frame link on the named output.

Re-read the working table. Check its width, text sizes, lowercase layer names, Fill/Hug settings, row-only borders, and chip text, position, and blue variable binding. Verify that the first `section` follows `screen` directly, that groups follow the source sections, and that long Arabic and English text wraps without clipping. Trace each candidate to an existing or newly written pair and check its casing, punctuation, and inline numbers. Reconcile the screens checked with the initial inventory.

Return the Figma section or table link, or its page and frame name if a link is unavailable. Report screens checked, new rows written, repeated occurrences skipped, and any unresolved work. For a screenshot without a destination, prepare the pairs and ask for the editable Figma page. Confirm a canvas handoff only after verifying it there.

## Text output when requested

For an explicit chat preview or export, use the same source sections and duplicate-skipping rules. In Markdown, put the screen name and status above the table. Use the first real section name as the Markdown table header. Put subsequent section names in bold in the first cell of their own row. Omit language labels. In an HTML export, use two equal columns, centered spanning section headings, row borders, and a borderless table wrapper. Set the table to `dir="ltr"` and each Arabic cell to `lang="ar" dir="rtl"`.

### Verify Mobile Number · In Progress

| **Verification form** | |
| :--- | ---: |
| Enter the Verification Code | أدخل رمز التحقق |
| Verification Code | رمز التحقق |
| We sent a code to your mobile number | أرسلنا رمزًا إلى رقم جوالك. |
| Didn’t receive the verification code? Request a new code in 00:59 | لم يصلك رمز التحقق؟ اطلب رمز جديد بعد: 00:59 |
| Resend Code | إعادة إرسال الرمز |
