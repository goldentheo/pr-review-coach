# Contributing to PR Review Coach
 
Thanks for your interest in improving the coach. Here's how to help.
 
## Ways to Contribute
 
### Report issues
 
If the coach handles a situation poorly — misses something obvious, gives bad advice, gets confused by a PR format — open an issue with:
 
- The PR link (if public) or a description of the PR structure
- What happened vs. what you expected
- Which phase of the session it occurred in
### Suggest improvements
 
Ideas for new review dimensions, better hint strategies, or missing edge cases are welcome. Open an issue describing what you'd change and why.
 
### Submit changes
 
1. Fork the repo
2. Edit `pr-review-coach/SKILL.md`
3. Test your changes by pasting the updated SKILL.md as a custom instruction in a Claude project and running through a few real PRs
4. Open a PR with a description of what you changed and a before/after example if possible
## Guidelines
 
- Keep the skill in a single `SKILL.md` file. Don't split it into multiple files unless there's a strong reason.
- Test with real PRs, not hypothetical ones. The skill should work well on messy, real-world code.
- The tone should stay conversational and supportive. This is a coach, not a grader.
- If adding a new review dimension or phase, make sure it's grounded in something that actually comes up in PRs — don't add checklist items for their own sake.
## Testing Your Changes
 
The best test is to use the skill on 2-3 real PRs of varying complexity:
 
- A small, clean PR (should handle gracefully without inventing problems)
- A medium PR with a few real issues
- A large PR (20+ files) to verify it focuses on the right files
Check that the session flow feels natural and the hints are calibrated well.
