# Assessment Notes

## Fix 1: Task Search Filter Bug
- Issue: The search query had incorrect AND/OR precedence.
- How I found it: I reviewed the TaskRepository search query.
- Fix: Grouped the title and description search conditions together.
- Why: This ensures archived and status filters are applied correctly to all search results.

## Fix 2: Unnecessary Request Delay
- Issue: The TaskController contained an artificial Thread.sleep delay.
- How I found it: I reviewed the request handling logic in TaskController.
- Fix: Removed the artificial delay and unused complexity calculation.
- Why: API requests should not be intentionally delayed.

## Fix 3: Invalid Status Handling
- Issue: An invalid task status could cause an exception.
- How I found it: I reviewed the TaskStatus.valueOf() usage.
- Fix: Added validation and return HTTP 400 for an invalid status.
- Why: Invalid client input should return a clear Bad Request response instead of causing a server error.