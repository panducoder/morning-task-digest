# Morning Task Digest

Scheduled remote agent that emails Preetam a prioritized, project-grouped task digest every morning at 9:30 AM IST.

## What it does

Each morning the remote agent scans the past 7 days across:

- Granola meeting transcripts
- Gmail (inbox, starred, sent/commitments)
- Slack (DMs, @mentions, threads)
- Google Calendar (upcoming 3 days + last 7 days prep follow-ups)
- Google Drive (doc comments tagging Preetam, pending shared doc responses)

Extracts both **explicit asks** (direct requests, assignments, commitments) and **implicit asks** (unanswered questions, pending replies).

Prioritizes as **P0 / P1 / P2**, groups by auto-detected **project cluster**, and emails the digest to `preetam.das@mindtickle.com`.

## Schedule

- Cron: `0 4 * * *` UTC = **9:30 AM Asia/Kolkata daily**
- Model: `claude-opus-4-7`
- Delivered via: Gmail connector

## Why a dedicated repo

The remote CCR agent needs a git source to clone. This repo is intentionally tiny — the logic lives in the trigger prompt itself. Drop follow-up automation scripts here if the digest grows.

## Managing the trigger

- View / edit / pause: https://claude.ai/code/scheduled
- Update via `/schedule` slash command in Claude Code
