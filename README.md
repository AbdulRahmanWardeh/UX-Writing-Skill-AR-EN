# UX-Writing-Skill-AR-EN

Document new Arabic interface copy from one screen, a selection, or an entire Figma page. The agent builds editable bilingual tables in Figma and groups the copy by the section where it appears. English is on the left and the exact Arabic is on the right.

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

A template is optional. The agent builds the table or detaches a supplied instance and fills it. To update an existing handoff, ask the agent to reformat it in place. If you start with a screenshot, provide an editable Figma destination for the handoff or ask for a Markdown preview.

## Figma table layout

Each table is **400 px** wide with a white background. Each row fills the table width and hugs its content height. The rows carry the light-grey borders and dividers. The table wrapper has no stroke.

| Figma row layer | Contents |
| --- | --- |
| `screen` | Screen name at **18 px** on the left and a blue **In Progress** chip at **16 px** on the right, with **Space between** |
| `section` | Centered **16 px** section name from the source screen, such as **Categories**, **Banner**, or **Services** |
| `row` | One English–Arabic pair at **16 px**, with wrapping in both cells |

The first section follows the screen heading directly. The table omits the “English / العربية” language-name row. Text, white surfaces, light-grey borders and separators, and the blue chip use the file’s design-system variables.

## English casing

Follow each element’s role on the source screen. A filter chip reads **Review Needed** and a status badge reads **Review needed**. A standalone success message reads **Changes Saved** and a toast reads **Changes saved**. In a source table, the heading **Payment Method** uses title case and the value **Bank transfer** uses sentence case. Each translated string keeps its casing in the handoff table.

English UI copy omits a final period. Arabic keeps its original punctuation. [Full casing rules](skills/ux-writing-ar-en/SKILL.md#apply-english-casing-and-punctuation)

## Example handoff

In this Home screen, the **Banner** section contains a title, description, and button. They stay together. Each English string follows the casing for its own role.

### Home · In Progress

| **Categories** | |
| :--- | ---: |
| Plumbing | سباكة |
| Electrical | كهرباء |
| View All | عرض الكل |
| **Banner** | |
| Need Help? | تحتاج إلى مساعدة؟ |
| Choose a service for your home | اختر خدمة لمنزلك. |
| Book a Visit | احجز زيارة |
| **Services** | |
| Home Maintenance | صيانة منزلية |

Read the full [SKILL.md](skills/ux-writing-ar-en/SKILL.md).
