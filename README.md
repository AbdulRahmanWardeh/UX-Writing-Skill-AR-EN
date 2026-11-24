# UX-Writing-Skill-AR-EN

Turn an Arabic product screen into a bilingual copy table. The agent keeps the original Arabic on the right, writes natural English on the left, and groups the rows by their role in the interface. It works from a screenshot or a design frame. Standalone numbers get no translation row. Numbers inside copy keep their original digits and formatting, as in «خلال ٧ أيام» → “Within ٧ days”.

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

Attach a screen and ask the agent to extract its copy.

> Extract the Arabic body copy from this screen and give me the English and Arabic in a table. Skip the screen header and footer.

Supply a Figma table with the screen or in a later message.

> Fill this table with the copy you extracted. Detach the table instance yourself and keep its typography, spacing, and Auto Layout.

Give the agent an editable Figma table for the second step. When you supply a main component, the agent creates and detaches a working instance. A screenshot alone is enough for the copy table in chat.

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
| **Buttons** | |
| Resend Code | إعادة إرسال الرمز |

The extraction rules, translation conventions, and Figma instructions are in [SKILL.md](skills/ux-writing-ar-en/SKILL.md).
