# GitHub Collector

> Collect GitHub data over time to get more insight.

## Insights

- My profile
    - Who are my stargazers?
    - Who started/removed starring over time?
- Which (public) repos do I own?
- Stargazers of repos
    - Who are the stargazers of my repos?
    - Who started/removed starring over time?

## Profile (`profile`)
- Every successful collector task updates each record with `modified_at = now()`
- Current amount of stargazers and favorites are stored in the profile

- `profile_id` - 
- `github_id` - 
- `followers` - 
- `following` - 
- `public_repos` - Total **current** amount of public repos
- `public_gists` - Total **current** amount of public gists
- `created_at` - Creation date of the profile on GitHub.
- `modified_at` - Date the profile was last updated on GitHub.
- `confirmed_at` - 

## Profile History (`profile_history`)


## Users (`users`)
General purpose table to store GitHub users, to use the across domains and potentially also tenants.
The table is more supposed to be a cache, then something alse

### Profile - Stargazers (`profile_stargazers`)
Store details who is stargazing the profile

- `profile_id` - Id of the profile, see table `profile`
- `stargazer_id` - Id of the user, see table `users`
- `created_at` - Should ideally be taken from the date when the user starte starring the profile.
- `modified_at` - For each time the stargazing can be confirmed, `modified_at` is updated ...
    
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
