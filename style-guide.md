# Style Guide

Time & Expense design system. Use token names — never raw hex — in component code.

---

## Color

### Brand

| Name  | Token          | Hex       |
|-------|----------------|-----------|
| Navy  | `--primary`    | `#0C1631` |
| Teal  | `--accent`     | `#0B7C7C` |
| Ice   | `--secondary`  | `#E8EDF7` |
| Frost | `--background` | `#F5F6F8` |

### Status Semantic

| Name      | Token              | Hex       |
|-----------|--------------------|-----------|
| Approved  | `--color-approved` | `#059669` |
| Pending   | `--color-pending`  | `#C47F17` |
| Rejected  | `--destructive`    | `#C92722` |
| Submitted | `--color-billable` | `#3B4FBF` |

### Domain — Time & Expense

| Name     | Token              | Hex       |
|----------|--------------------|-----------|
| Time     | `--color-time`     | `#0B7C7C` |
| Expense  | `--color-expense`  | `#C47F17` |
| Billable | `--color-billable` | `#3B4FBF` |
| Overhead | `--chart-4`        | `#7C3AED` |

### UI Surface

| Name       | Token                | Value              |
|------------|----------------------|--------------------|
| Card       | `--card`             | `#FFFFFF`          |
| Muted      | `--muted`            | `#E8EDF7`          |
| Muted Text | `--muted-foreground` | `#6B7897`          |
| Border     | `--border`           | `rgba(12,22,49,.1)`|

---

## Typography

**UI copy:** Plus Jakarta Sans  
**Data values, amounts, durations:** JetBrains Mono

| Level     | Size              | Weight   | Usage                                   |
|-----------|-------------------|----------|-----------------------------------------|
| Display   | 2.25rem / 36px    | 700      | Hero headings, empty states             |
| H1        | 1.5rem / 24px     | 600      | Page titles, section headers            |
| H2        | 1.25rem / 20px    | 600      | Card titles, panel headings             |
| H3        | 1rem / 16px       | 600      | Subsection labels, table groups         |
| Body      | 0.875rem / 14px   | 400      | Descriptions, form labels, content      |
| Caption   | 0.75rem / 12px    | 400      | Metadata, timestamps, helper text       |
| Mono Data | 0.875rem / 14px   | 400–500  | All numeric data values (JetBrains Mono)|

---

## Spacing

4px base unit. Use multiples of 4 for all padding, margin, and gap values.

| px   | Scale | Usage                             |
|------|-------|-----------------------------------|
| 4px  | 1     | Inline gap, icon padding          |
| 8px  | 2     | Inline gap, icon padding          |
| 12px | 3     | Component padding, stack spacing  |
| 16px | 4     | Component padding, stack spacing  |
| 24px | 6     | Section gap, card padding         |
| 32px | 8     | Section gap, card padding         |
| 48px | 12    | Section separation, page margin   |
| 64px | 16    | Section separation, page margin   |
| 96px | 24    | Section separation, page margin   |

---

## Border Radius

| Value   | Usage                    |
|---------|--------------------------|
| 2px     | Tight chips              |
| 4px     | Cards, inputs, buttons (default) |
| 6px     | Modals, popovers         |
| 8px     | Feature cards            |
| 9999px  | Status pills             |

---

## Buttons

Use the `Button` component from `ui/button`. Never write raw `<button>` elements.

### Variants

| Variant      | Appearance                          | Example usage         |
|--------------|-------------------------------------|-----------------------|
| Primary      | Navy fill, white text               | Log Time, Start Timer |
| Secondary    | White fill, border, dark text       | Add Expense           |
| Outline      | Transparent fill, border            | Submit Sheet, View All|
| Destructive  | Red fill, white text                | Delete                |
| Ghost/Link   | No fill, no border, arrow optional  | View report →         |

### Sizes

| Size    | Description                              |
|---------|------------------------------------------|
| Large   | Full-width or primary CTA                |
| Default | Standard action                          |
| Small   | Secondary / compact context              |
| Icon    | Square icon-only (edit, delete actions)  |

### Loading State

Show a spinner + "Submitting…" label. Button remains disabled and muted.

### Domain Icon Actions

Pair icon left of label for domain-specific actions: Start Timer (clock), Log Expense ($), View Calendar (calendar), Add Category (tag).

---

## Form Controls

Use the `Input`, `Select`, and `Textarea` components. Never write raw `<input>` elements.

### Text Inputs

- Label sits above the field
- Placeholder text uses `--muted-foreground`
- Prefix icon for currency: `$` symbol inside the input left edge
- **Error state:** red border (`--destructive`) + error message in red below the field, marked with `*` on the label

### Selects & Textarea

- Dropdown chevron on the right
- Textarea for free-form multi-line notes
- Same border and label treatment as text inputs

### Toggles & Checkboxes

- Checkbox: filled teal (`--accent`) when checked
- Toggle switch: teal when on, muted gray when off
- Labels always to the right of the control

### Disabled States

- All controls: grayed out, no pointer events
- Disabled button label: "Entry Locked", uses muted fill
- Read-only inputs look identical to disabled but are labeled "(read-only)"

---

## Badges & Alerts

Status badges use custom colors. Category chips use the outline Badge variant with a color dot.

### Status Badges

| Status       | Color   |
|--------------|---------|
| Approved     | Green   |
| Pending      | Amber   |
| Submitted    | Indigo  |
| Under Review | Indigo/Purple |
| Rejected     | Red     |
| Draft        | Gray    |
| Reimbursed   | Teal    |
| Archived     | Gray    |

Each pill: colored dot + label, pill background is a light tint of the status color, border matches the dot color.

### Category Chips

Outline Badge variant with a solid colored square dot. Example categories and their colors:

| Category    | Color  |
|-------------|--------|
| Development | Teal   |
| Design      | Purple |
| Meetings    | Teal   |
| Travel      | Amber  |
| Meals       | Green  |
| Software    | Red    |
| Training    | Blue   |
| Admin       | Gray   |

### System Badge Variants (shadcn/ui)

Primary (filled dark) · Secondary (gray) · Outline · Destructive (red). Can include leading icons (clock, dollar sign).

### Alerts

| Type    | Icon          | Border/Background |
|---------|---------------|-------------------|
| Info    | ℹ circle      | Blue tint         |
| Success | ✓ circle      | Green tint        |
| Warning | △ triangle    | Amber tint        |
| Error   | ⊗ circle-x   | Red tint          |

Structure: bold title on first line, description text below in regular weight.

---

## Progress Bars

Used for budget utilization, hour targets, and project caps.

### Structure

```
Label                         $2,840 / $3,500
████████████████████░░░  81%  Approaching limit
```

- Label: Body weight 400 left
- Value: Mono Data right-aligned (`$current / $max` or `Xh Xm / Xh`)
- Percentage: Caption, below bar left
- Status note: Caption, below bar right

### Threshold Colors

| Range   | Color | Status label         |
|---------|-------|----------------------|
| 0–75%   | Green (`--color-approved`) | On track |
| 75–90%  | Amber (`--color-pending`)  | Near limit / Approaching limit |
| 90%+    | Red (`--destructive`)      | Over budget — action required |

---

## KPI Cards

Dashboard stat tiles. Each shows a primary metric, a contextual sub-label, and a trend or progress indicator.

### Anatomy

```
┌─────────────────────────────────┐
│ Label                    [icon] │
│ Primary metric (large, mono)    │
│ Sub-label in caption            │
│ ▓▓▓▓▓▓▓▓▓▓▓░░░░░  progress bar │
│ ↗ Trend text in caption         │
└─────────────────────────────────┘
```

- Icon: top-right, in a lightly tinted pill (domain color)
- Primary metric: H1 weight, JetBrains Mono for numbers
- Progress bar: colored by threshold (see Progress Bars section)
- Trend: green for positive delta, amber/muted for neutral or negative

---

## Time Entry Patterns

List rows for logged time. Shows project, task, duration (mono), billable flag, status badge, and actions.

### Running Timer Row

```
[clock] Project — Task name        --:----  [Start]
        Started 2h 14m ago · Billable
```

- Clock icon avatar, muted ring
- Timer display uses JetBrains Mono, dashed when not running
- Start button: primary variant

### Log Row

```
[■] Task name — subtask      $ Billable   3:00  ● Approved
    Project · Mon Jul 27
```

- Colored square (project color) left
- Task name bold, project/date in caption below
- Billable flag: muted "$" label
- Duration: JetBrains Mono
- Status badge: pill with dot
- Row hover reveals edit/delete icon buttons

---

## Expense Entry Patterns

Expense rows show category chip, merchant, amount (mono), receipt status, and approval state.

### Row Structure

```
[$] Merchant name            Travel  [receipt]  $24.50  ● Approved   Jul 27
    Description — detail
```

- Dollar icon in teal circle avatar
- Merchant name bold, description in caption below
- Category chip: colored outline
- Receipt icon: indicates attachment present (warning icon if missing)
- Amount: JetBrains Mono, bold
- Status badge + date right-aligned

### Footer

```
5 expenses  ⚠ 1 missing receipt          Total: $660.70
```

---

## Data Tables

Use tabular mono type for all numeric columns. Status columns get badge chips. Action columns appear on row hover.

### Column Header Style

- ALL CAPS, small size, `--accent` or `--primary` teal color
- Columns: DATE · PROJECT · TASK · DURATION · BILLABLE · AMOUNT · STATUS

### Cell Rules

| Column Type  | Treatment                              |
|--------------|----------------------------------------|
| Date         | JetBrains Mono, muted                 |
| Text         | Body, regular weight                  |
| Duration     | JetBrains Mono, right-aligned         |
| Amount       | JetBrains Mono, right-aligned         |
| Boolean      | Check icon (green) or dash (–)        |
| Status       | Badge pill with dot                   |
| Actions      | Icon buttons, visible on row hover only |

### Footer

```
5 entries · Week 30              10:45        $1,281.25
```

Caption weight, totals right-aligned in mono.

---

## Charts & Data Viz

Use **Recharts**. Chart colors map to `--chart-1` through `--chart-5`. All axis labels use JetBrains Mono.

### Chart Color Tokens

| Token      | Name             | Hex       | Semantic use                      |
|------------|------------------|-----------|-----------------------------------|
| `--chart-1`| Time / Teal      | `#0B7C7C` | Logged hours, time metrics        |
| `--chart-2`| Expense / Amber  | `#C47F17` | Costs, budget items               |
| `--chart-3`| Billable / Indigo| `#3B4FBF` | Billable work, revenue            |
| `--chart-4`| Overhead / Violet| `#7C3AED` | Non-billable, internal            |
| `--chart-5`| Approved / Emerald|`#059669` | Approved, on-track                |

### Chart Patterns

- **Grouped bar:** Logged vs Billable hours. Ghosted bar (logged) + filled bar (billable) per day.
- **Donut:** Expense breakdown by category. Legend to the right with percentages.
- **Line/area:** Monthly trends. Subtle fill under the line, no markers.

---

## Status System

Every entity (time entry, expense, timesheet) has a defined set of states. Use these exact colors and labels — do not invent custom status styles.

### Timesheet State Machine

```
Draft → Submitted → Approved
                         ↓
                     Rejected → Draft (edit & resubmit) → Submitted
```

| State     | Description                                         |
|-----------|-----------------------------------------------------|
| Draft     | Saved locally, not yet submitted. Editable.         |
| Submitted | Sent for manager review. Read-only until decision.  |
| Approved  | Confirmed by manager. Locked and processed for payroll. |
| Rejected  | Returned with feedback. Can be corrected and resubmitted. |

### Expense State Machine

```
Draft → Submitted → Under Review → Approved → Reimbursed
                                ↓
                            Rejected
```

| State        | Description                                              |
|--------------|----------------------------------------------------------|
| Draft        | Not submitted. All fields editable.                      |
| Submitted    | In the approval queue. Awaiting first review.            |
| Under Review | Finance team reviewing receipts and policy compliance.   |
| Approved     | Verified and approved. Queued for reimbursement.         |
| Rejected     | Does not meet policy. Returned with rejection reason.    |
| Reimbursed   | Payment processed. Final state — no further changes.     |

### Budget Utilization Thresholds

| Label      | Range  | Color | Action                            |
|------------|--------|-------|-----------------------------------|
| On Track   | 0–75%  | Green | Budget spend is healthy. No action needed. |
| Near Limit | 75–90% | Amber | Approaching budget cap. Review upcoming spend. |
| Over Budget| 90%+   | Red   | Budget exceeded. Requires manager approval. |

---

## Status Rules

1. **One status badge per row** — never show two status pills on the same table row; combine or prioritize.
2. **Always use pills for status** — status is never conveyed by row background color alone; always pair with a labeled pill.
3. **Dot color = border color = text color family** — each status has one source color; use its tint for background and border.
4. **Mono font for counts** — numbers next to status (e.g. "7 pending") always use JetBrains Mono.
5. **Rejected requires a reason** — always surface the rejection message inline or on expand.
6. **Final states are immutable** — Approved (timesheet) and Reimbursed (expense) are locked; remove all edit affordances.
