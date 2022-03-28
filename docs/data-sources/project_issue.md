---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gitlab_project_issue Data Source - terraform-provider-gitlab"
subcategory: ""
description: |-
  The gitlab_project_issue data source allows to retrieve details about an issue in a project.
  Upstream API: GitLab API docs https://docs.gitlab.com/ee/api/issues.html
---

# gitlab_project_issue (Data Source)

The `gitlab_project_issue` data source allows to retrieve details about an issue in a project.

**Upstream API**: [GitLab API docs](https://docs.gitlab.com/ee/api/issues.html)

## Example Usage

```terraform
data "gitlab_project" "foo" {
  id = "foo/bar/baz"
}

data "gitlab_project_issue" "welcome_issue" {
  project = data.gitlab_project.foo.id
  iid     = 1
}

output "welcome_issue_web_url" {
  value = data.gitlab_project_issue.web_url
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `iid` (Number) The internal ID of the project's issue.
- `project` (String) The name or ID of the project.

### Optional

- `id` (String) The ID of this resource.

### Read-Only

- `assignee_ids` (Set of Number) The IDs of the users to assign the issue to.
- `author_id` (Number) The ID of the author of the issue. Use `gitlab_user` data source to get more information about the user.
- `closed_at` (String) When the issue was closed. Date time string, ISO 8601 formatted, for example 2016-03-11T03:45:40Z.
- `closed_by_user_id` (Number) The ID of the user that closed the issue. Use `gitlab_user` data source to get more information about the user.
- `confidential` (Boolean) Set an issue to be confidential.
- `created_at` (String) When the issue was created. Date time string, ISO 8601 formatted, for example 2016-03-11T03:45:40Z. Requires administrator or project/group owner rights.
- `description` (String) The description of an issue. Limited to 1,048,576 characters.
- `discussion_locked` (Boolean) Whether the issue is locked for discussions or not.
- `discussion_to_resolve` (String) The ID of a discussion to resolve. This fills out the issue with a default description and mark the discussion as resolved. Use in combination with merge_request_to_resolve_discussions_of.
- `downvotes` (Number) The number of downvotes the issue has received.
- `due_date` (String) The due date. Date time string in the format YYYY-MM-DD, for example 2016-03-11.
**Note:** removing a due date is currently not supported, see https://github.com/xanzy/go-gitlab/issues/1384 for details.
- `epic_id` (Number) ID of the epic to add the issue to. Valid values are greater than or equal to 0.
- `epic_issue_id` (Number) The ID of the epic issue.
- `external_id` (String) The external ID of the issue.
- `human_time_estimate` (String) The human-readable time estimate of the issue.
- `human_total_time_spent` (String) The human-readable total time spent of the issue.
- `issue_id` (Number) The instance-wide ID of the issue.
- `issue_link_id` (Number) The ID of the issue link.
- `issue_type` (String) The type of issue. Valid values are: `issue`, `incident`, `test_case`.
- `labels` (Set of String) The labels of an issue.
- `links` (Map of String) The links of the issue.
- `merge_request_to_resolve_discussions_of` (Number) The IID of a merge request in which to resolve all issues. This fills out the issue with a default description and mark all discussions as resolved. When passing a description or title, these values take precedence over the default values.
- `merge_requests_count` (Number) The number of merge requests associated with the issue.
- `milestone_id` (Number) The global ID of a milestone to assign issue. To find the milestone_id associated with a milestone, view an issue with the milestone assigned and use the API to retrieve the issue's details.
- `moved_to_id` (Number) The ID of the issue that was moved to.
- `references` (Map of String) The references of the issue.
- `state` (String) The state of the issue. Valid values are: `opened`, `closed`.
- `subscribed` (Boolean) Whether the authenticated user is subscribed to the issue or not.
- `task_completion_status` (List of Object) The task completion status. It's always a one element list. (see [below for nested schema](#nestedatt--task_completion_status))
- `time_estimate` (Number) The time estimate of the issue.
- `title` (String) The title of the issue.
- `total_time_spent` (Number) The total time spent of the issue.
- `updated_at` (String) When the issue was updated. Date time string, ISO 8601 formatted, for example 2016-03-11T03:45:40Z.
- `upvotes` (Number) The number of upvotes the issue has received.
- `user_notes_count` (Number) The number of user notes on the issue.
- `web_url` (String) The web URL of the issue.
- `weight` (Number) The weight of the issue. Valid values are greater than or equal to 0.

<a id="nestedatt--task_completion_status"></a>
### Nested Schema for `task_completion_status`

Read-Only:

- `completed_count` (Number)
- `count` (Number)

