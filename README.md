# UX-Writing-Skill-AR-EN

Turn an Arabic product screen into a bilingual copy table. The agent keeps the original Arabic on the right, writes natural English on the left, and groups the rows by their role in the interface. It works from a screenshot or a design frame.

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

## Example handoff

For a verification screen with «رجوع» in the app header and «الرئيسية» in the footer, the table contains only the copy inside the form.

### Mobile verification

| English | العربية |
| :--- | ---: |
| **Title** | |
| Enter the verification code | أدخل رمز التحقق |
| **Buttons** | |
| Resend code | إعادة إرسال الرمز |

The extraction rules, translation conventions, and Figma instructions are in [SKILL.md](skills/ux-writing-ar-en/SKILL.md).
