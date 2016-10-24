# GitHub Collector

> Collect GitHub data over time to get more insight.

## Insights

- My profile
    - Who are my stargazers?
    - Who started/removed starring over time?
- Which repos do I own?
- Stargazers of repos
    - Who are the stargazers of my repos?
    - Who started/removed starring over time?

## Profile (`github_profile`)
- Every successful collector task updates each record with `modified_at = now()`
- Current amount of stargazers and favorites are stored in the profile

### Profile - Stargazers (`github_profile_stargazers`)
Store details who is stargazing the profile

- `profile_id`
- `stargazer_id`
- `date_created`
- `date_modified` - For each time the stargazing can be confirmed, `date_modified` is updated ...

    
    
## Repos

- Every successful collector task updates each record with `modified_at = now()`
- Keep the repo even if it was deleted
    - Deleted repos get flagged with `is_deleted = true`
    - This requires to go through all repos after updating them and marking them as deleted
- Store per day (`github_repos_history`)
    - Stargazers per repo => `github_repos_history.stargazers`
        - repo_id
        - stargazer_id
        - date_created
        - date_removed (null by default)
    - Amount of watchers
    - Amount of forks
    - Amount of pull requests
    - Amount of issues

### Repo tables

- `github_repos` - Current state of each repo
- `github_repos_history` - Full history of each repo
