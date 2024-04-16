# ChatGPT custom instructions
## Committing
Each commit that changes `custom_instruc.md` MUST ensure that `custom_instrc.md` has:

1. Unix (`\n`) line endings
2. 
    - 2 lines breaks (`\n\n`) after every paragraph
    - 1 line break (`\n`) after every markdown section heading
    - 1 line break (`\n`) at the end of file
3. no spellcheck errors, except those that I specifically allow (eg. "mathy").

## Git tagging
Each commit that changes `custom_instruc.md` MUST be tagged with metadata equal to the first 6 hexdigits of `git hash-object custom_instruc.md`.

Increment the PATCH number with new changes.

Increment the MINOR number if I revert to a previous version of `custom_instruc.md`, and thus the 6-hexdigit hash prefix is the same.

For example, "Initial commit" is tagged v0.0.1+780f38, where `780f38` is obtained by ([from StackOverflow](https://stackoverflow.com/questions/460297/git-finding-the-sha1-of-an-individual-file-in-the-index)):

```bash
git hash-object custom_instruc.md
```

## ChatGPT chat tagging
For each new conversation, as soon as ChatGPT generates its first response and a conversation title, tag the conversation title by prefixing it with the 6-hexdigit hash prefix.

For example, the conversation "Grandfather age 7" is renamed "780f38 Grandfather age 7".
