# Source Policy

Provider: YouTube

Policy snapshot: 2026-09-04. Reverify all live conditions before adapter work.

## Planned official surfaces

- read: public_search
- read: channels
- read: videos
- read: playlists
- read: comments
- read: owned_captions
- read: owned_analytics
- publication-plan target: video
- publication-plan target: short
- publication-plan target: thumbnail
- publication-plan target: caption_track
- publication-plan target: scheduled_video
- deferred: community_post
- deferred: third_party_caption_download

## Admission rules

- Official provider APIs and authorized accounts only.
- Every observation records source identity, time, URL, and permission basis.
- Account allowlists and topic allowlists are explicit configuration.
- Rate, quota, cost, retention, deletion, and review obligations fail closed.
- HTML scraping, session-cookie automation, CAPTCHA bypass, and stealth collection are out of scope.
- API success does not establish public visibility or consumer acceptance.

## Current provider boundary

Public metadata is distinct from owner-only analytics and captions. Uploads require OAuth, resumable transfer, processing-state observation, and current project-audit checks; Community posts are not assumed to be API-publishable.

Official documentation: https://developers.google.com/youtube/v3/
