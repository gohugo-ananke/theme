You are working on the `gohugo-ananke/ananke` GitHub repository.

Goal: select, analyse, and fix or triage one GitHub issue from Ananke.

Input handling:

* If the user provides an issue ID, use that specific issue:
  `https://github.com/gohugo-ananke/ananke/issues/$ID`
* If the user does not provide an issue ID, inspect the open issues at:
  `https://github.com/gohugo-ananke/ananke/issues`
  and choose one suitable issue to work on.
* Wherever an instruction contains `$ID`, replace `$ID` with the actual selected issue number.

Required actions:

1. Check the issue list or the specific issue URL.
2. Select the issue:
   * If `$ID` is provided, select issue `$ID`.
   * If no `$ID` is provided, choose one open issue that appears narrow, verifiable, and fixable.
3. Analyse the issue.
4. Print a concise summary of the issue.
5. Print a proposed solution.
6. Determine whether the issue is fixable:
   * If it is fixable, continue with the implementation.
   * If it is not fixable, explain why clearly and stop. Do not hallucinate a solution.
7. Check the repository contribution instructions:
   * Prefer `CONTRIBUTING.md`.
   * If the repository uses another documented contribution file such as `CONTRIBUTIONS.md`, follow that instead.
8. Create a branch in `https://github.com/gohugo-ananke/ananke/` according to the contribution instructions.
   * If no better branch name is obvious, use:
     `issues/$ID`
9. Add the changes required to fix the issue.
10. Create a pull request against the `development` branch.
    * Always use `development` as the PR base branch.
    * Do not open pull requests against `main`.
    * Do not push directly to `main` or `development`.
11. Link the pull request to the issue or related discussion.
   * Use `Closes #$ID`, `Fixes #$ID`, or another appropriate GitHub closing keyword when the PR fully resolves the issue.
   * Use `Refs #$ID` when the PR is related but does not fully close the issue.
12. Explain the fix, including:
   * What changed.
   * Why it fixes the issue.
   * Any files touched.
   * Any assumptions made.
   * Any verification performed.

Clarification rule:

* If required information is missing and cannot be inferred safely, ask for clarification before making repository changes.
* If the issue is ambiguous but still triageable, state the ambiguity and propose the safest next action.
* Do not invent repository structure, implementation details, test results, or maintainer intent.

Output format:

1. `Selected issue`
2. `Issue summary`
3. `Proposed solution`
4. `Implementation`
5. `Pull request`
6. `Verification`
7. `Notes or blockers`

Behaviour requirements:

* Be precise and evidence-based.
* Prefer small, reviewable changes.
* Always open PRs against `development`, never against `main`.
* Do not push directly to protected branches.
* If direct pushes are blocked or inappropriate, create a branch and open a pull request.
* If tooling reports an error, explain the error and adapt the workflow.
* If the selected issue is better closed as invalid, duplicate, already fixed, or not planned, explain the probable close reason and do not create a fake fix.