# New Tab Hub

**Keep tabs on your tabs — now with a launcher.**

New Tab Hub is a Chrome extension that replaces your new tab page with a dashboard of everything you have open. Tabs are grouped by domain, with homepages (Gmail, X, LinkedIn, etc.) pulled into their own group. Close tabs with a satisfying swoosh + confetti.

It also adds a **launcher** at the top of the dashboard: a Google search box, a WeChat search box (via Sogou), Feishu quick-create buttons, and a quick-links grid — restoring the things a default new tab page is good for.

No server. No account. No external API calls beyond the search/create links you click. Just a Chrome extension.

> **Fork notice.** This is a fork of [zarazhangrui/tab-out](https://github.com/zarazhangrui/tab-out) by Zara Zhang (MIT). It adds a launcher with Google + WeChat search and Feishu quick-create. All credit for the original tab-grouping dashboard goes to the upstream project.

---

## Install with a coding agent

Send your coding agent (Claude Code, Codex, etc.) this repo and say **"install this"**:

```
https://github.com/DarcyZhu/new-tab-hub
```

The agent will walk you through it. Takes about 1 minute.

---

## Features

- **See all your tabs at a glance** on a clean grid, grouped by domain
- **Homepages group** pulls Gmail inbox, X home, YouTube, LinkedIn, GitHub homepages into one card
- **Close tabs with style** with swoosh sound + confetti burst
- **Duplicate detection** flags when you have the same page open twice, with one-click cleanup
- **Click any tab to jump to it** across windows, no new tab opened
- **Save for later** bookmark tabs to a checklist before closing them
- **Localhost grouping** shows port numbers next to each tab so you can tell your vibe coding projects apart
- **Expandable groups** show the first 8 tabs with a clickable "+N more"
- **100% local** your data never leaves your machine
- **Pure Chrome extension** no server, no Node.js, no npm, no setup beyond loading the extension

### Added in this fork — the launcher

- **Google search box** type and hit Enter to search Google in the current tab
- **WeChat search box** search WeChat official-account articles via Sogou (`weixin.sogou.com`), the standard browser entry point for WeChat content
- **Feishu quick-create** one-click new docx / sheet / base / mindnote (uses the generic `my.feishu.cn` tenant — self-hosted Feishu tenants may need to edit the URLs in `app.js`)
- **Quick links** pinned custom links plus Chrome's most-visited sites, deduped

---

## Manual Setup

**1. Clone the repo**

```bash
git clone https://github.com/DarcyZhu/new-tab-hub.git
```

**2. Load the Chrome extension**

1. Open Chrome and go to `chrome://extensions`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Navigate to the `extension/` folder inside the cloned repo and select it

**3. Open a new tab**

You'll see Tab Out.

---

## How it works

```
You open a new tab
  -> Tab Out shows your open tabs grouped by domain
  -> Homepages (Gmail, X, etc.) get their own group at the top
  -> Click any tab title to jump to it
  -> Close groups you're done with (swoosh + confetti)
  -> Save tabs for later before closing them
```

Everything runs inside the Chrome extension. No external server, no API calls, no data sent anywhere. Saved tabs are stored in `chrome.storage.local`.

---

## Tech stack

| What | How |
|------|-----|
| Extension | Chrome Manifest V3 |
| Storage | chrome.storage.local |
| Sound | Web Audio API (synthesized, no files) |
| Animations | CSS transitions + JS confetti particles |

---

## License

MIT

---

Built by [Zara](https://x.com/zarazhangrui). Fork with launcher additions maintained by Darcy Zhu.
