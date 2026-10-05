# Publishing checklist

This repository is public and permanent. Anything pushed here can be copied,
cached, and indexed within minutes — deleting it later does not un-publish it.
Run through this list before every commit.

## Never publish

- [ ] Client or prospect names, abbreviations, or code names (including in
      file names, branch names, commit messages, issue titles, and links)
- [ ] Links to private repositories, issues, tickets, drives, or dashboards
- [ ] People's names, emails, phone numbers, or usernames (other than the repo owner's public GitHub handle)
- [ ] Real data: exports, CSVs, screenshots, logs, record IDs, invoice/lease/PO
      numbers, addresses, amounts tied to a real party
- [ ] System identifiers: hostnames, tenant/account IDs, URLs of internal systems
- [ ] Secrets: API keys, tokens, passwords, connection strings, `.env` files
- [ ] Contract terms, pricing, or anything under NDA

## Always do

- [ ] Write specs as **patterns** ("a property manager needs to…"), not case
      studies ("Client X needed to…")
- [ ] Replace any real example with obviously fictional data (`Acme Corp`,
      `example.com`, `555-0100`, round numbers)
- [ ] Copy content in as new files — never fork, merge, or cherry-pick from a
      private client repository (that would bring its history along)
- [ ] Commit with your GitHub `noreply` email
      (`git config user.email "<id>+<user>@users.noreply.github.com"`)
- [ ] Re-read the full diff (`git diff --staged`) before pushing

## If something slips through

1. Make the repository private immediately (Settings → General → Danger Zone).
2. Rotate any exposed secret — assume it is compromised.
3. Remove it from history (or delete and recreate the repository), then
   decide whether to make it public again.
