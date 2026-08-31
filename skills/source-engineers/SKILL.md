---
name: source-engineers
description: Source software engineers from GitHub for an open role, from a brief or a job post, and follow up on the shortlist.
---
Use this when someone wants to hire, source or find engineers.

## Turning a request into a search

Pass `technology`, `location` and `role` yourself whenever the request makes them obvious. Fall back to `query` alone only for a free-form job description.

One request, one call to `search_developers`. Results are already filtered on the location asked for, so a short list means the index holds no more people there, not that the search failed. Never repeat the search with a wider or different location to lengthen a list: it spends another of the user's searches and returns people who are not where they asked. Say the list is short and ask first.

## Reading the results

Rank on what the tool returns: contributions over the last twelve months, the languages in someone's own repositories, ownership of their most visible project, and recency. Star and follower counts measure attention on a project, not the work of a person, and they never decay. Do not present them as a ranking.

Say plainly when a profile is thin. A short honest list beats a padded one.

## Contact details

Each profile carries whichever public route that developer chose to publish, an email or a LinkedIn profile, sometimes neither. Report what is there. Never suggest looking up an address in git commit history: it is public because git records a commit author, not because the person published it.

## Writing the first message

When asked to draft outreach, use what the search returned: the repository they ship to, the languages in their own projects, when they last pushed. One specific sentence about their work, the role, who is writing, and a way out. If you cannot name what they built, say so instead of writing a template.

## Following up

`save_candidate` puts someone in the user's pipeline, `to_contact` by default and `contacted` only if the user says they already reached out. `list_pipeline` answers who is waiting and who has been contacted.
