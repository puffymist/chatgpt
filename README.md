# ChatGPT custom instructions
## Committing
Each commit that changes `custom_instruc.md` MUST ensure that `custom_instruc.md` has:

1. Unix (`\n`) line endings
2. 
    - 2 lines breaks (`\n\n`) after every paragraph
    - 1 line break (`\n`) after every markdown section heading
    - 1 line break (`\n`) at the end of file
3. no spellcheck errors, except those that I specifically allow (eg. "mathy").

## Git tagging
Each commit that changes `custom_instruc.md` MUST be tagged if I have a ChatGPT conversation using that version of custom instructions. Otherwise, tagging is optional.

The tag uses a modified form of semantic versioning:

- metadata: the first 6 hexdigits of `git hash-object custom_instruc.md`
- PATCH: increment with each tag
- MINOR: increment if I revert to a previous version of `custom_instruc.md`, and thus the 6-hexdigit hash prefix is the same again.

For example, "Initial commit" is tagged v0.0.1+780f38, where `780f38` is obtained by ([from StackOverflow](https://stackoverflow.com/questions/460297/git-finding-the-sha1-of-an-individual-file-in-the-index)):

```bash
git hash-object custom_instruc.md
```

## ChatGPT conversation tagging
For each new conversation, as soon as ChatGPT generates its first response and a conversation title, tag the conversation title by prefixing it with the 6-hexdigit hash prefix.

At that point, tagging the commit becomes mandatory and the tagged commit (and the tag) MUST NOT be subsequently deleted or modified.

I also additionally tag with the following categories:

- `llm`: About ChatGPT itself, custom instructions and prompting, and other usage questions.
- `test`: Probing ChatGPT's capabilities.

- `info`: Using ChatGPT like a search engine. Asking questions that have definite, non-frontier answers, but which are hard to google.
- `phil`: Conceptual questions. Having fun.

- `prac`: Questions I asked for a practical purpose, including practical things that I might or might not actually do.
- `me`: As with `prac`, but about my personal wellbeing and performance.

- `src`: Programming questions.

After the tags, the title itself should be Capitalised for ease of parsing visually, but I may leave it in lowercase if that would be more recognisable and easier to read.
