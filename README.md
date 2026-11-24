# UX-Writing-Skill-AR-EN

Document Arabic interface copy from one screen, a selection, or an entire Figma page. The agent creates editable bilingual tables on the canvas, with English on the left and the exact Arabic on the right. Each screen contributes only copy that still needs documenting.

## Install

From the project where you want to use the skill, run the following command.

```sh
npx skills add AbdulRahmanWardeh/UX-Writing-Skill-AR-EN --skill ux-writing-ar-en
```

For a local checkout next to your project, use its path instead.

```sh
npx skills add ../UX-Writing-Skill-AR-EN --skill ux-writing-ar-en
```

### Claude Code marketplace

To use the marketplace installation, run these commands inside Claude Code.

```text
/plugin marketplace add AbdulRahmanWardeh/UX-Writing-Skill-AR-EN
/plugin install ux-writing-ar-en@ux-writing-skills
```

## Use the skill

With an editable Figma page, try this prompt.

> Translate every screen on this page and create the bilingual tables in Figma. Skip anything already documented on this page.

For a single screen, try this prompt.

> Document the new copy on this screen. Check the earlier screens’ translation tables first.

If screen 1 already documents the button **استمرار → Continue**, the same button on screen 2 is **skipped entirely**. Screen 2 gets a table only if it has other, new copy. Running the skill again on an unchanged page adds zero rows.

The agent can process a page with 50+ screens in one request. It reads existing handoffs to check for duplicates and excludes those tables from source extraction. Product tables inside screens, such as payment history, still contribute their labels and text. Screen headers, footers, and standalone numbers are skipped. An inline number such as `00:59` stays in its sentence with its original digits, even when the timer has its own Figma layer.

The agent designs the table using the file’s color variables for solid text, a white background, and light-grey borders and separators. A template is optional. If you provide a table instance, the agent detaches and fills it. If you start with a screenshot, provide an editable Figma destination for the canvas handoff or ask for a Markdown preview.

## English casing

Follow each element’s role on the source screen. A filter chip reads **Review Needed** and a status badge reads **Review needed**. A standalone success message reads **Changes Saved** and a toast reads **Changes saved**. In a source table, the heading **Payment Method** uses title case and the value **Bank transfer** uses sentence case. Each translated string keeps its casing in the handoff table.

English UI copy omits a final period. Arabic keeps its original punctuation. [Full casing rules](skills/ux-writing-ar-en/SKILL.md#apply-english-casing-and-punctuation)

## Example handoff

For a verification screen with «رجوع» in the app header and «الرئيسية» in the footer, the table contains only the copy inside the form.

### Mobile Verification

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

The extraction rules, translation conventions, and Figma instructions are in [SKILL.md](skills/ux-writing-ar-en/SKILL.md).
