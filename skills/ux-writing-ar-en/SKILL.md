---
name: ux-writing-ar-en
description: Extract Arabic body copy from screenshots or design frames, skip screen headers and footers, and translate the copy into English. Use when documenting Arabic UI strings in a bilingual table or filling a detached instance of a supplied Figma table component.
---

# Arabic to English UX writing

Create one bilingual copy table for each supplied screen or state. Place English on the left and the original Arabic on the right. Treat a supplied table or layout example as the destination format. Take the source strings from the screen the user identifies.

## Read the screen

1. Identify the screen body using the frame hierarchy when available or the visible layout in a screenshot. Exclude the entire screen header and footer, including their titles, navigation labels, buttons, links, and legal text. Include section headings, buttons, and consent text that belong to the body, even near a screen edge. For example, capture «متابعة» inside a form and skip it inside a footer. Apply this boundary to the source screen only.
2. Name the output using the supplied screen or frame name, or derive a short English heading from the body. Use “Screen 1”, “Screen 2”, and so on if the purpose is unclear. If the body contains no Arabic copy, report that and leave the destination as it is.
3. Transcribe every visible Arabic body string exactly, including spelling, punctuation, diacritics, numerals, and any Latin text within the same string. Join visual line wraps within one label or paragraph. Give independently displayed elements their own rows, even when two controls use the same words.
4. Group elements by function. Use only headings supported by the body, such as **Title**, **Descriptions**, **Buttons**, **Field labels**, **Placeholders**, **Helper text**, **Errors**, **Success messages**, **Navigation**, **Statuses**, or **Terms**. Order groups by first appearance. Within a group, follow the Arabic reading order, top to bottom and right to left within a row.
5. If text is cropped or illegible, keep the readable fragment and mark the gap with `⟦غير مقروء⟧` in Arabic and `⟦unreadable⟧` in English. If the body is missing or unreadable, ask for a clearer image.

## Write the English

- Translate what each element does. Use a concise verb for a button, a noun phrase for a field label, and a clear statement for a message. For example, translate the button «تأكيد الدفع» as “Confirm Payment” and the toast «تم تأكيد الدفع» as “Payment confirmed”.
- Reuse approved English wording and product terminology. Apply the casing for the element’s role. Preserve the official spelling of brands, proper names, and acronyms in either case, including “Shop by Motory”, “Apple Pay”, and “OTP”.
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

## Fill a supplied table component

Prepare the bilingual rows first. If the user provides the component or instance in a later message, reuse the prepared rows for that screen. When given an editable table, perform the detachment and fill the cells yourself using the host editor’s existing canvas access.

1. Resolve the supplied table component or instance. Use the requested destination, or free space beside the source frame on its editable work page. If only a library component is supplied and the destination is unclear, ask for the work page and provide the prepared rows. Inspect the template’s screen-name field, section headings, and language cells. Preserve its styles, spacing, dividers, column widths, and Auto Layout.
2. If the user supplies a standalone table instance to fill, detach that instance in place. If they supply the main component, create an instance of the supplied variant at the destination and detach the new instance. Duplicate first when the user identifies an instance as a reusable template, or when it sits inside another instance or a component definition. Detach that working copy outside the enclosing component structure. In Figma’s Plugin API, continue on the editable frame returned by `detachInstance()`. Reuse an already detached output frame, including on a retry.
3. Fill the screen name and each section heading. Duplicate the template’s section and data rows as needed, and remove unused sample rows from the working table. Enter one English–Arabic pair per row. Keep English left-aligned in the left cell and Arabic right-aligned, reading RTL, in the right cell. Preserve inline link styling and let longer text wrap. Load the text layers’ existing fonts before editing through the Plugin API.
4. Re-read the completed rows and inspect the layout. Verify that the working table is detached, every body string has its English counterpart, and each copy row traces to an occurrence inside the source body. Check for clipped text and leftover placeholders.

If the target is only a screenshot, the editing connection is unavailable, or edit access is missing, return the prepared rows in chat and say what is needed to place them in the file. For a partial edit, identify the working table and the rows still to fill.

## Format the handoff

- Render the screen name above the copy. Show a review status beside it only when the user or the supplied handoff explicitly identifies that screen’s status. Use the template’s badge styling, or green for **Final** in other styled output. Hide a sample **Final** badge until the screen has that status. Treat a status shown to the app’s user in the body as a translatable string.
- In HTML or a rich document, use one table per screen with two equal-width columns and thin dividers. Put the screen name at the upper left, the optional review status at the upper right, and center each bold section heading across both columns. In HTML, set the table to `dir="ltr"` and each Arabic cell to `lang="ar" dir="rtl"`. Align English left and Arabic right.
- In Markdown chat, use the screen name as a heading, then one two-column table. Put each section name in bold in the first cell of its own row. Use the following excerpt as a formatting example.

### Verify Mobile Number

| English | العربية |
| :--- | ---: |
| **Title** | |
| Enter the Verification Code | أدخل رمز التحقق |
| **Field labels** | |
| Verification Code | رمز التحقق |
| **Helper text** | |
| We sent a code to your mobile number | أرسلنا رمزًا إلى رقم جوالك. |
| **Buttons** | |
| Resend Code | إعادة إرسال الرمز |

Compare each row with the source body. Check the English case against the element’s role, confirm each English string omits a final full stop, and match the Arabic punctuation to the source. Check small print, inline links, repeated labels, and Arabic–English pairing. After a verified canvas edit, return the table link or its page and frame name. For a chat handoff, return the screen headings and tables, with a brief access note only if a requested canvas edit is pending.
