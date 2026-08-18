# Updating ExamAce legal documents

The app downloads `terms-of-use.md` and `privacy-policy.md` directly from this
directory. Keep both metadata comments at the top of each document.

For every edit, update `legal-version` to a new date or revision identifier.

For a minor edit that does not require renewed user acceptance, keep the
existing `acceptance-version` unchanged:

```markdown
<!-- legal-version: 2026-09-02 -->
<!-- acceptance-version: 1 -->
```

For a material legal update, increment `acceptance-version` by one. Users who
have not accepted that generation will be asked to review and accept it before
continuing in the main app:

```markdown
<!-- legal-version: 2026-10-01 -->
<!-- acceptance-version: 2 -->
```

Acceptance versions are monotonic. Never decrease one or reset it to `0` after
a generation requiring acceptance has been published. Minor revisions after a
material update must continue using that material update's acceptance version.

Version `0` is the bundled launch baseline and does not trigger an additional
acceptance dialog.
