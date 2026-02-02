# Bug Buzz

**Bug Buzz** automates bug and fix request reporting in Slack.

Users submit bugs through a Slack form, and Bug Buzz automatically routes each report to the correct project channel (and optionally other tools) so teams can take action quickly.

---

## How It Works

Bug Buzz uses AWS serverless services to process and route bug reports reliably.

- **AWS Lambda** handles event-driven logic (processing bug reports)
- **Amazon SQS** queues bug reports to prevent data loss during traffic spikes
- **Amazon SNS** broadcasts bug events to multiple systems
- **Slack API** collects reports and posts updates

---

## Bug Report Flow

1. User submits a bug report in Slack  
2. Lambda receives the event and stores it in SQS  
3. Another Lambda formats and routes the message  
4. The report is posted to the correct Slack channel  
5. *(Optional)* SNS triggers integrations like Jira, email, or GitHub issues

---

## Tech Stack

- AWS Lambda
- Amazon SQS
- Amazon SNS
- Slack API
- (Optional) OctoKit / GitHub API
