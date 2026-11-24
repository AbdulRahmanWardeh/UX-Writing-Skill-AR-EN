---
name: ux-writing-ar-en
description: Extract Arabic UX copy from a screen, screenshot, or an entire Figma page, including pages with 50+ screens. Skip copy already translated on the same Figma page and build editable English–Arabic handoff tables in Figma with the file’s color variables. Use for bilingual UI copy audits, handoffs, or filling a supplied table component.
---

# Arabic to English UX writing

For a Figma screen, selection, or page, deliver editable bilingual tables on the design canvas. Build the table yourself when the user supplies only the source. Put English on the left and the exact Arabic source on the right. A screen gets a new table only when it contributes new copy.

## Identify the source screens and earlier translations

1. Work within the source Figma page. For a single screen or selection, also inspect the page for earlier screens and their handoff tables. Write only for the requested screens. For a whole page, snapshot the IDs of **all** source screens and states, including those in nested sections and outside the viewport, before creating any output. Follow the user’s flow or numbered screen order when available. Otherwise use canvas reading order, top to bottom and right to left within a row, with a stable frame ID as a tie-breaker.
2. Inventory existing translation tables separately. Recognize a generated table by its output marker or source-frame link. Recognize older handoffs by their screen heading, paired English–Arabic columns, section rows, and placement. Use these cues together. Exclude handoff tables, their wrapper sections, reusable copy-table templates, and all their descendants from source extraction. A product table **inside a source screen**, such as payment history, still contributes its headings and body copy. Skip component libraries and reference boards unless the user designates them as source screens.
3. Read completed Arabic–English pairs from the identified handoffs for lookup. Associate a table with its source frame ID, or with an unambiguous screen name and location in older files. For a single screen, use its own existing rows and rows documented for earlier screens on this page. For a whole-page pass, seed the lookup with completed rows already present on the page and give each new string to its first eligible screen in flow order. Ignore sample rows, incomplete pairs, and copy on other pages. Seeing Arabic on an earlier screen without a documented English translation does not count as a match.
4. For a page of 50 or more screens, process the complete snapshot in manageable batches within the same request. Carry the translation lookup and the list of covered frame IDs across every batch. Recheck the destination before appending after an interruption, retain verified work, and continue from the first unfinished screen. Count a duplicate-only screen as covered.

## Read the screen

1. Identify the screen body using the frame hierarchy when available or the visible layout in a screenshot. Exclude the entire screen header and footer, including their titles, navigation labels, buttons, links, and legal text. Include section headings, buttons, and consent text that belong to the body, even near a screen edge. For example, capture «متابعة» inside a form and skip it inside a footer. Apply this boundary to the source screen only.
2. Use the supplied screen or frame name, or derive a short English heading from the body. Use “Screen 1”, “Screen 2”, and so on if the purpose is unclear. If the body has no translatable copy, record that screen as checked and continue.
3. Assemble each complete label, sentence, or paragraph in Arabic reading order **before** filtering numbers or creating rows. Keep every number that belongs to the message in that same row, including a countdown introduced by «بعد:» or a quantity such as «٧ أيام». Join inline fragments even when the number is bold, updates live, wraps to another line, or occupies its own Figma text layer.
4. After grouping, skip a numeric value that stands on its own, such as a page number or the year in a separate model-year field. Keep the independent field label. Transcribe each complete Arabic message exactly, including its spelling, punctuation, diacritics, numerals, and Latin text. Treat each independent message or control as a candidate for one row.
5. Group elements by function. Use only headings supported by the body, such as **Title**, **Descriptions**, **Buttons**, **Field labels**, **Placeholders**, **Helper text**, **Errors**, **Success messages**, **Navigation**, **Statuses**, or **Terms**. Order groups by first appearance. Within a group, follow the Arabic reading order, top to bottom and right to left within a row.
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

1. Choose the user’s destination if supplied. Otherwise place a single table in clear space beside its screen. For a page, place the tables together in a dedicated **UX Copy — EN / AR** section in unused space on the same page, in source order. Reuse an existing output section and the table associated with each source frame. Keep source screens and main components intact.
2. With no template, create a native editable Auto Layout frame for each screen with new rows. Name it **UX Copy — <screen name>**. Put the screen name at the top and center each bold role heading across both columns. For each pair, create one horizontal row with two equal-width flexible cells. Put English in a left-aligned LTR text layer on the left and Arabic in a right-aligned RTL text layer on the right. Set a readable table width, let both texts wrap, and size rows to the taller cell. Use the file’s text styles and spacing. Give the table a thin outer border and 1 px row and column dividers. Include a review status only when explicitly supplied for that screen.
3. If a table is supplied, inspect and reuse its layout. Detach a designated output instance in place. For a main component, create an instance of the supplied variant at the destination and detach that instance. For a reusable or nested template, make a working copy outside its parent before detaching it. Reuse an already detached frame. Work on the editable frame returned by `detachInstance()` when using the Plugin API. Duplicate the working template’s rows as needed, remove unused samples, and preserve its layout and typography. If the component arrives after extraction, use the prepared rows.
4. Resolve the actual **color variables available in this file** once per page. Use the file’s semantic names, collections, active mode, and bindings on comparable elements to identify the roles below. The names shown here describe roles and can differ from the names in the file.

   | Part of the table | File color variable to bind |
   | --- | --- |
   | All text, including the screen name, section headings, and both language cells | Solid text |
   | Table background and any opaque header, row, or cell surface | White background |
   | Outer border, row dividers, and center divider | Light-grey line or separator. If the file defines separate variables, bind the border to line and the dividers to separator |

   Apply the variables as bindings to fills or strokes, including on a supplied table. A matching hex value alone does not establish a binding. If a role is missing or ambiguous, finish preparing the copy, identify the unresolved role, and ask for its variable. Keep the affected styling pending until it can be bound.
5. Load the required fonts before editing text through the Plugin API. Write each pair into native text layers and preserve inline link styling. Mark the output section and tables so a later run can recognize them. Store the source page and frame IDs on each table in persistent node metadata when available. Otherwise use a consistent output name and retain an explicit link to the source frame. Keep markers on the handoff.
6. Re-read the written pairs and their variable bindings. Verify left/right placement, complete Arabic text, English casing and punctuation, inline numbers in the same pair, wrapping without clipping, and absence of sample rows. For each covered screen, each candidate must resolve to a verified existing pair or a newly written pair. Reconcile the number of checked screens with the initial inventory and report any remaining screens or rows by name.

Return a link to the Figma section or table, or its page and frame name if no link is available. Summarize screens checked, new rows written, and repeated occurrences skipped. If all copy was already documented, link to the existing handoff. If the input is only a screenshot and the destination is unknown, prepare the pairs and ask for the editable Figma page. If the editor cannot write, preserve the prepared work and identify exactly what is pending. A canvas handoff is complete only after the rows and styling have been verified there.

## Text output when requested

When the user explicitly asks for a chat table, preview, or export, apply the same extraction and duplicate-skipping rules to the available sources. In Markdown, put the screen name above a two-column table and each section name in bold in the first cell of its own row. For an HTML export, use equal columns, centered section headings, and thin dividers. Set the table to `dir="ltr"` and each Arabic cell to `lang="ar" dir="rtl"`.

### Verify Mobile Number

| English | العربية |
| :--- | ---: |
| **Title** | |
| Enter the Verification Code | أدخل رمز التحقق |
| **Field labels** | |
| Verification Code | رمز التحقق |
| **Helper text** | |
| We sent a code to your mobile number | أرسلنا رمزًا إلى رقم جوالك. |
| Didn’t receive the verification code? Request a new code in 00:59 | لم يصلك رمز التحقق؟ اطلب رمز جديد بعد: 00:59 |
| **Buttons** | |
| Resend Code | إعادة إرسال الرمز |
