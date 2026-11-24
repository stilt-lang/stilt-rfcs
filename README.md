# Stilt RFCs

A change to the Stilt language starts here, as an RFC: a document that says what the change is, shows the program a user would write, states the rules as a change to the [Reference](https://github.com/stilt-lang/stilt/tree/main/reference), and shows the error messages that go with it. The project's [governance](https://github.com/stilt-lang/stilt/blob/main/GOVERNANCE.md) says who decides: the benevolent dictator decides every RFC, after the discussion and the final comment period described below.

## What needs an RFC

- A new feature of the language, or a change to what an existing one means.
- A change to a rule of the Reference that changes what some program does or which programs are rejected.
- A change to the standard library's contract ([the Reference's `std` chapter](https://github.com/stilt-lang/stilt/blob/main/reference/17-std.md)): a new module, or a change to what a function promises.
- A change to what a package's API is, to the editions, or to what a release promises to keep ([the Reference's versions chapter](https://github.com/stilt-lang/stilt/blob/main/reference/21-versions.md)).
- A change to the command-line interface's behaviour that scripts depend on.

These don't: a bug fix that makes an implementation agree with the Reference, a clarification of a paragraph that changes no program's meaning, a new or better message, a document, a test, a refactoring, an optimisation. Those are pull requests to the [main repository](https://github.com/stilt-lang/stilt). If you aren't sure, ask in an issue first.

## Before you write one

Most good ideas start as an issue here, titled with the problem and not the solution: "I can't write X without Y". An idea is discussed until someone, usually its author, can write the plain example. An RFC that begins with a solution looking for a problem is sent back to the issue.

## An RFC holds

Copy [`0000-template.md`](0000-template.md) to `text/0000-short-name.md` and fill in every section:

1. **A summary.**
2. **A plain example first**: the program a user would write, what it does, and what goes wrong without the feature. Stilt's design is decided from plain examples, so this is what the dictator reads first, and what the discussion argues about.
3. **The motivation**: who needs this and how often.
4. **The rules**, as a diff of the Reference: the paragraphs added, changed or removed, each with its ID.
5. **The error tax**: draft diagnostics for the feature's common mistakes, in the form the compiler would print them, each showing the fix in the code. An RFC without them isn't ready, because a feature whose mistakes can't be explained is not finished.
6. **Compatibility**: whether it breaks code, which edition it belongs to, and the `stilt migrate` rewrite that moves a program across it.
7. **Alternatives and unresolved questions.**

## The states of an RFC

1. **Draft.** The author opens a pull request that adds `text/0000-short-name.md`, as a draft. Anyone may comment. The author revises until the RFC is complete.
2. **Discussion.** The author marks the pull request ready. A maintainer is named review manager, and the RFC is given the next number, `0001` for the first, and its file renamed. The discussion happens on the pull request. The review manager keeps a summary of the open questions at the top, and decides when the discussion has stopped producing new arguments.
3. **Final comment period.** The review manager announces the proposed outcome, accept or decline, and a period of ten days in which anyone may raise an objection that the discussion has not already weighed. A significant change to the text restarts the ten days.
4. **Accepted or declined.** The dictator decides and writes the reasons on the pull request. An accepted RFC is merged and its status becomes `accepted`. A declined one is closed with the reasons, and stays readable.
5. **Implemented.** The change is made first in the Reference's paragraphs, then in the tests, the reference interpreter and the compiler, as [CONTRIBUTING.md](https://github.com/stilt-lang/stilt/blob/main/CONTRIBUTING.md) says. When the pull requests that do it have merged, the RFC's status becomes `implemented`, and it links them.
6. **Stable.** A release contains the change and its release notes name the RFC. The status becomes `stable` with that release's version.

An accepted RFC records why the language is as it is. After it is implemented, the Reference is the definition: it is not edited to match an RFC, and an RFC is not edited to match the Reference, except to record its status and links.

## Conduct

Discussion follows the project's [Code of Conduct](https://github.com/stilt-lang/stilt/blob/main/CODE_OF_CONDUCT.md). Argue with the proposal, not with the person who made it.

## Licence

The text of the RFCs is under [CC BY 4.0](LICENSE-CC-BY-4.0). The programs in them are under the [MIT](LICENSE-MIT) and [Apache 2.0](LICENSE-APACHE) licences, at your option.
