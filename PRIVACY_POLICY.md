# Privacy Policy — Video Player & Reels Controls for Facebook™

**Effective Date:** October 29, 2026

**Extension Name:** Video Player & Reels Controls for Facebook™  
**Supported Browsers:** Google Chrome and Mozilla Firefox

## 1. Overview

Video Player & Reels Controls for Facebook™ (the "Extension") is a browser extension designed to improve the experience of watching Facebook videos, Watch content, and Reels.

We respect your privacy and aim to minimize data collection.

**The Extension does not use developer-operated analytics, advertising trackers, or external servers to collect personal information. It does not sell or share your personal data with advertisers or data brokers.**

Player preferences, optional watch history, and playback positions are stored locally in your browser.

The Extension communicates with Facebook and its media delivery services when necessary to retrieve and play videos.

## 2. Information Stored Locally

The Extension uses your browser's built-in extension storage APIs to save information needed for its functionality.

### 2.1 Player Preferences

The following settings may be stored locally:

- Preferred video quality and playback speed
- Volume and player preferences
- Auto-open and autoplay settings
- Player configuration and feature preferences

These settings remain in your browser's extension storage and are not uploaded to developer-operated servers.

### 2.2 Watch History and Playback Positions

Watch history and resume positions are enabled by default and can be disabled separately in the popup. When enabled, the Extension may save:

- Previously watched Facebook video references and metadata
- Playback progress and resume timestamps
- Information needed to reopen recently watched videos

This information is stored locally in your browser.

The history contains at most 20 entries. Resume positions are limited to 200 entries; positions older than 30 days are ignored, but this age check does not immediately delete the stored records.

Disabling history stops new history entries; it does not erase existing history. Clear or remove history entries in the popup to delete them and their corresponding resume records. Disabling “Resume where I left off” removes all ordinary resume records. The separate mini-player handoff described below is not cleared by these controls.

### 2.3 Temporary Session Data

To improve playback performance, the Extension may temporarily cache:

- Video stream URLs and metadata
- Available playback quality information
- Video and Reel navigation queues
- Temporary information needed to resolve media streams

This information is used for playback and caching and is not intentionally transmitted to developer-operated servers.

In Chrome, resolved-stream caches and per-tab queues use `chrome.storage.session`, which is cleared when the browser session ends. Queue data is removed when its tab closes. Expired cache entries are ignored when read; cleanup is not a guarantee of immediate erasure.

**Persistent mini-player handoff:** To restore the mini-player or comments view after navigation, the Extension separately writes the current video route, title/metadata, signed media URLs and manifest, playback time, paused state, and handoff timestamp to `chrome.storage.local` under `miniSession`. This record can survive a browser restart. It is eligible for restoration for 30 minutes; it is removed when an expired record is next read, on expansion to the full player, or when the extension is removed. Closing an active mini-player may save a final handoff during teardown. It is not automatically erased by a timer. This handoff can be saved even when watch history or ordinary resume saving is disabled.

Browsers without session storage may use local storage for navigation queues.

### 2.4 Private Browsing

The Extension is designed to avoid saving watch history and resume positions while operating in supported Incognito or Private Browsing sessions.

Mini-player handoffs are also not written from Incognito tabs. Preferences can still be stored and shared with normal browsing. In-memory feed caches and Chrome session caches are not partitioned by the Extension between normal and Incognito tabs; enabling Incognito access does not mean all temporary data is isolated. Other browser-level behavior depends on the browser and its configuration.

## 3. Network Requests and Facebook Content

To provide video playback features, the Extension communicates with Facebook and its associated media delivery services, including:

- `facebook.com`
- `fbcdn.net`
- `fbsbx.com`

These requests may be required to:

- Retrieve video and Reel information
- Resolve available media streams
- Load video, audio, and subtitle content
- Display Facebook comments
- Refresh expired playback URLs
- Retrieve information for user-initiated downloads

Requests can also occur automatically when hovering a supported link, prefetching neighboring videos, or discovering upcoming Reels, before you play the prefetched video. Video-page fallback resolution and media downloads normally omit credentials; Reels-feed discovery uses credentialed Facebook requests. Facebook may process those requests, including the requested video URLs, according to its own privacy practices. This is not an offline-only extension.

**The Extension does not operate a separate backend service for collecting or storing your browsing history, video history, or playback preferences.**

## 4. Browser Permissions

The Extension requests browser permissions necessary for its features.

### Storage

Used to store player settings, optional watch history, resume positions, and temporary playback information.

### Downloads

Used for user-initiated progressive MP4 downloads and their progress reporting. Merged DASH files and PNG screenshots are saved through browser blob links or, where supported, a user-selected file handle rather than the downloads API.

### Scripting

Used to support the enhanced video player and dynamically load playback functionality where required.

### Declarative Network Requests

Used to support network request handling and fallback mechanisms for retrieving Facebook media streams.

### Context Menus

Used to provide a right-click option for opening supported Facebook videos and Reels in the enhanced player.

### Website Access

The Extension requests access to relevant Facebook domains and associated media content delivery domains.

This access is necessary to identify supported video content, retrieve playback information, and provide enhanced controls.

## 5. Video Downloads and Screenshots

The Extension allows users to download supported video content and capture screenshots.

Where supported, separate video and audio streams may be processed and combined into a standard MP4 file directly within your browser.

This processing does not require uploading the media to a developer-operated conversion server.

Downloaded files and screenshots are saved to a location managed by your browser or selected by you.

Users are responsible for ensuring that their downloading and use of content comply with applicable laws and the rights of content owners.

## 6. Third-Party Services

The Extension interacts with Facebook and its associated media delivery infrastructure to provide its functionality.

Facebook content and related network requests are subject to Meta Platforms, Inc.'s own policies and terms.

For more information, please review:

https://www.facebook.com/privacy/policy/

The Extension does not intentionally collect or transmit your Facebook password or authentication credentials to the extension developer.

Your browser may automatically include session cookies or other authentication information in requests to Facebook, as part of normal authenticated browsing.

The Extension is not affiliated with, endorsed by, or sponsored by Meta Platforms, Inc.

## 7. Analytics, Advertising, and Data Sharing

The Extension does not include developer-operated analytics or advertising trackers.

We do not:

- Sell personal information
- Share user data with advertisers
- Build advertising profiles
- Upload locally stored watch history to developer-operated servers
- Use personal data for targeted advertising

Network requests made directly to Facebook and its media services are separate from developer-operated data collection.

## 8. Data Retention and User Control

Locally stored preferences and optional watch history may remain available until they are cleared, expire under the Extension's retention rules, or the Extension is removed.

You can manage your data by:

- Disabling optional watch history
- Clearing saved watch history and playback positions
- Changing Extension preferences
- Removing the Extension from your browser

Session-storage caches and the persistent `miniSession` handoff have different retention behavior, described in section 2.3. Clearing watch history does not clear this handoff; expanding to the full player removes the stored handoff, while closing an actively playing mini-player can save a final handoff during teardown in the current version. Removing the Extension clears its extension storage. Downloads already saved on disk must be deleted separately.

## 9. Children's Privacy

The Extension is not specifically designed for children and does not knowingly collect children's personal information through a developer-operated service.

Use of Facebook remains subject to Meta's age requirements and policies.

## 10. Changes to This Privacy Policy

We may update this Privacy Policy to reflect changes in the Extension's functionality, browser requirements, or applicable privacy practices.

When changes are made, the Effective Date at the top of this document will be updated.

## 11. Contact and Support

For questions about this Privacy Policy, extension functionality, or privacy concerns, visit our public support repository:

- **Support:** https://github.com/git-sujon/video-player-reels-controls-support
- **Bug reports and questions:** https://github.com/git-sujon/video-player-reels-controls-support/issues

GitHub issues are public. Do not include passwords, access tokens, cookies, signed media URLs, private Facebook content, or other sensitive personal information in an issue. For questions that should not be posted publicly, use the developer contact information shown on the extension's store listing.

This Privacy Policy applies to **Video Player & Reels Controls for Facebook™** distributed through supported browser extension stores, including Mozilla Firefox Add-ons and the Chrome Web Store.