#Contributing to KRATE

If you wish to add a new assembly, please make sure the assembly targets .NET Standard 2.0.

Pull Requests

    DO submit all code changes via pull requests (PRs) rather than through a direct commit. PRs will be reviewed and potentially merged by the repo maintainers after a peer review that includes at least one maintainer.
    DO NOT submit "work in progress" PRs. A PR should only be submitted when it is considered ready for review and subsequent merging by the contributor.
    DO give PRs short-but-descriptive names (e.g. "Improve code coverage for System.Console by 10%", not "Fix #1234")
    DO refer to any relevant issues, and include keywords that automatically close issues when the PR is merged.
    DO tag any users that should know about and/or review the change.
    DO ensure each commit successfully builds.
    DO address PR feedback in an additional commit(s) rather than amending the existing commits, and only rebase/squash them when necessary. This makes it easier for reviewers to track changes.
    DO assume that "Squash and Merge" will be used to merge your commit unless you request otherwise in the PR.
    DO NOT fix merge conflicts using a merge commit. Prefer 'git rebase'.
    DO NOT mix independent, unrelated changes in one PR. Separate real product/test code changes from larger code formatting/dead code removal changes. Separate unrelated fixes into separate PRs, especially if they are in different assemblies.

# C# Coding Style

For non code files (xml, etc), our current best guidance is consistency. When editing files, keep new code and changes consistent with the style in the files. For new files, it should conform to the style for that component. If there is a completely new component, anything that is reasonably broadly accepted is fine.

An EditorConfig file (.editorconfig) has been provided at the root of the repository, enabling C# auto-formatting conforming to the following guidelines.

The general rule is "use Visual Studio defaults".

    1. Use Allman style braces, where each brace begins on a new line. A single line statement block can go without braces but the block must be properly indented on its own line and must not be nested in other statement blocks that use braces. One exception is that a using statement is permitted to be nested within another using statement by starting on the following line at the same indentation level, even if the nested using contains a controlled block.
    2. Use four spaces of indentation (no tabs).
    3. Use _camelCase for internal and private fields and use readonly where possible. Prefix internal and private instance fields with _, static fields with s_ and thread static fields with t_. When used on static fields, readonly should come after static (e.g. static readonly not readonly static). Public fields should be used sparingly and should use PascalCasing with no prefix when used.
    4. Avoid using keyword 'this'. unless absolutely necessary.
    5. Always specify the visibility, even if it's the default (e.g. private string _foo not string _foo). Visibility should be the first modifier (e.g. public abstract not abstract public).
    6. Namespace imports should be specified at the top of the file, outside of namespace declarations, and should be sorted alphabetically, with the exception of System.* namespaces, which are to be placed on top of all others.
    7. Avoid more than one empty line at any time. For example, do not have two blank lines between members of a type.
    8. Avoid spurious free spaces. For example avoid if (someVar == 0)..., where the dots mark the spurious free spaces. Consider enabling "View White Space (Ctrl+E, S)" if using Visual Studio to aid detection.
    9. If a file happens to differ in style from these guidelines (e.g. private members are named m_member rather than _member), the existing style in that file takes precedence.
    10. Only use var when it's obvious what the variable type is (e.g. var stream = new FileStream(...) not var stream = OpenStandardInput()).
    11. Use language keywords instead of BCL types (e.g. int, string, float instead of Int32, String, Single, etc) for both type references as well as method calls (e.g. int.Parse instead of Int32.Parse).
    12. Use PascalCasing to name all our constant local variables and fields. The only exception is for interop code where the constant value should exactly match the name and value of the code you are calling via interop.
    13. Use nameof(...) instead of "..." whenever possible and relevant.
    14. Fields should be specified at the top within type declarations.
    15. When including non-ASCII characters in the source code use Unicode escape sequences (\uXXXX) instead of literal characters. Literal non-ASCII characters occasionally get garbled by a tool or editor.
    16. When using labels (for goto), indent the label one less than the current indentation.

# Unit Test

	1. If you find a component that does not have a unit test. Please write a unit test for it.
	2. If you create a new component please write a unit test for it as well.
	3. If you edit an existing component and the changes required the unit test be change, please make the necessary edits to the unit test.