# Contact import example

This is an illustrative conversation with invented facts. It demonstrates the intended interaction; it is not a recorded user session or a test result.

The discussion concerns new contacts with unique email addresses. Handling an email address already present in the address book is a separate, unresolved decision.

## Establish the situation

**User:** Help me decide how a contact import should handle invalid rows. I want people to be able to start using the valid contacts without fixing the whole spreadsheet first.

**Agent:** You have already given a preference for keeping valid contacts usable. Let's make its consequences concrete. In this hypothetical product, an import currently saves nothing if any row is invalid. Suppose a spreadsheet contains 300 new contacts: 288 have valid email addresses and 12 have no email address. None matches an existing contact. What should the importer see and be able to do after uploading it?

**User:** Save the 288 and list the 12 that failed. Let me fix and retry those rows.

## Compare the same cases

**Agent:** Your proposal makes valid rows available immediately. The alternative is to hold the whole file until all rows pass. Let's compare both using the same facts and two criteria: which contacts are available, and what correction work remains.

| Scenario | Save valid rows immediately | Hold the entire file |
| --- | --- | --- |
| 288 valid rows, 12 missing email | 288 contacts available; 12 rows need correction | No contacts available; 12 rows need correction before all 300 can be saved |
| All 300 rows valid | All 300 available; no corrections | All 300 available; no corrections |
| All 300 rows missing email | No contacts available; all rows need correction | No contacts available; all rows need correction |

**Agent:** Saving valid rows fits the goal you described. It also means the result must clearly say which rows were saved, so a person does not mistake a partial import for a complete one. Holding the file keeps each upload all-or-nothing, but delays valid contacts. I recommend saving the valid rows with a clear result and a correction path. Does that trade-off fit?

**User:** Yes. Show "288 imported, 12 need correction" and let me download just the rejected rows with the reasons. For this feature, a syntactically valid email is required; the contact's name is optional. Importing a contact must not send any message. We have not decided what to do about an email already in the address book.

## Check the agent's interpretation

**Agent:** Then a contact with a valid email but no name should be saved, because the name is optional. It should count among the imported contacts, and no message should be sent. Is that your intended result?

**User:** Yes. Do not label the missing name as an error either.

**Agent:** Agreed. Here is a different variation: a row contains an email value, but its syntax is invalid. I would reject that row, give the invalid email as the reason, and still save other valid rows. Is that right?

**User:** Yes.

## Close and preserve the remaining decision

**Agent:** For new contacts with unique addresses, we have agreed:

- Save rows with syntactically valid email addresses; a missing name is acceptable and is not an error.
- Reject missing or malformed email addresses and report the reason for each rejected row.
- Show saved and rejected counts separately and offer a download of rejected rows for correction.
- Importing does not send messages.

The mixed, all-valid, and all-invalid cases follow the same rule. The missing-name and malformed-email variations also match your expectations.

We still need to decide how existing addresses and retries interact, so I cannot yet treat the complete import-and-retry feature as ready to build. We can continue with that decision or leave it explicitly unresolved. Does this summary capture what we settled?

**User:** Yes. Keep the existing-address and retry behavior open for our next discussion. This was a design discussion; do not implement it yet.

The settled behavior can be carried into a larger workflow, together with the unresolved blocker. See [using the skill with Matt's workflow](../docs/matt-workflow.md).
