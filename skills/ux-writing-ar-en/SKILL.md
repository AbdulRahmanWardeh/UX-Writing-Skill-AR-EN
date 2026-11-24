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

- Translate what each element does. Use a concise verb for a button, a noun phrase for a field label, and a clear statement for a status. For example, translate the action «تأكيد الدفع» as “Confirm payment” and the status «تم تأكيد الدفع» as “Payment confirmed”.
- Use natural, sentence-case English. Reuse explicitly approved English copy for the same element, and follow supplied product terminology. For Shop by Motory screens, use “Shop by Motory” for «شوب من موتري».
- Carry over amounts, currencies, deadlines, conditions, negation, and who takes the action. Keep placeholders such as `{amount}`, `{{name}}`, and `%s` intact.
- Keep a consent statement in one row with each linked phrase in its sentence. Underline the corresponding words where supported. Add a hyperlink only when its destination is supplied.

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

### Verify mobile number

| English | العربية |
| :--- | ---: |
| **Title** | |
| Enter the verification code | أدخل رمز التحقق |
| **Buttons** | |
| Resend code | إعادة إرسال الرمز |

Compare each row with the source body. Check small print, inline links, repeated labels, and Arabic–English pairing. After a verified canvas edit, return the table link or its page and frame name. For a chat handoff, return the screen headings and tables, with a brief access note only if a requested canvas edit is pending.
