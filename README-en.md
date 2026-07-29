# Hx0 DataGuard

[![Chrome Web Store](https://img.shields.io/badge/Chrome%20Web%20Store-v1.0.7-4285F4?style=flat-square&logo=googlechrome&logoColor=white)](https://chromewebstore.google.com/detail/hx0-%E6%95%B0%E6%8D%AE%E5%8D%AB%E5%A3%AB/hkhjbfajliglkonhfpkfkkdcdobikfig)
![Firefox AMO](https://img.shields.io/badge/Firefox%20AMO-Under%20Review-FF7139?style=flat-square&logo=firefoxbrowser&logoColor=white)
![Form](https://img.shields.io/badge/Form-Browser%20Extension-007AFF?style=flat-square)
![Computation](https://img.shields.io/badge/Computation-Local%20Processing-4CAF50?style=flat-square)
![Privacy](https://img.shields.io/badge/Privacy-No%20Page%20Content%20Upload-0D9488?style=flat-square)
![New Users](https://img.shields.io/badge/New%20Users-1--Day%20Trial%20VIP-FF9500?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-Sensitive%20Data%20Detection-E879F9?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-API%20Path%20Discovery-3B82F6?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-Phishing%20Email%20Detection-2563EB?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-Input%20Leak%20Prevention-EC4899?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-Rule%20Center-5856D6?style=flat-square)
![Feature](https://img.shields.io/badge/Feature-Report%20Export-0EA5E9?style=flat-square)
[![License](https://img.shields.io/badge/License-See%20LICENSE-8E8E93?style=flat-square)](LICENSE)

[简体中文](README.md) · **English**

> A local security assistant in your browser — scan pages for risks, identify phishing emails, prevent input leaks in real time, and export reports with one click.

**Now available on the [Chrome Web Store](https://chromewebstore.google.com/detail/hx0-%E6%95%B0%E6%8D%AE%E5%8D%AB%E5%A3%AB/hkhjbfajliglkonhfpkfkkdcdobikfig)** (project version 1.0.7) · Firefox v1.0.7 submitted for review, launching soon · Firefox v1.0.3 now available

## What It Is

Hx0 DataGuard is a **local** security assistant extension that runs in your browser. As you browse the web and use your mailbox every day, it quietly does three things for you in the background:

<img width="1672" height="941" alt="1 0 7-en" src="https://github.com/user-attachments/assets/dc64b230-b3fc-4fc9-a42f-32eed6389ec2" />


- **Looks outward**: scans the current page and its scripts to find sensitive data exposed in plaintext and clues about API endpoints
- **Guards inward**: as you type or paste into AI chats, forms, and chat boxes, it detects sensitive information before sending, then reminds or blocks
- **Vets emails**: fully offline analysis of webmail, downloaded or manually imported EML files — extracting identity, links, attachments, and delivery evidence to help identify phishing emails

All scan and detection results are stored **locally on your computer** by default. Page content and email bodies are never uploaded, making it suitable for personal office protection, security self-checks, and report archiving.

---

## Background

We have noticed two increasingly common problems:

**First, AI-assisted work makes "accidentally sending sensitive information" much easier.** More and more people paste logs, configurations, and customer data directly into chat boxes like ChatGPT, ERNIE Bot, and Doubao. Once sent, the content often cannot be recalled; manually redacting it section by section is both slow and error-prone.

**Second, auditing the frontend exposure surface is still fragmented.** When security testers run self-checks on authorized websites, they often have to switch between multiple tools just to find hardcoded keys, debug endpoints, and API paths that should never appear on the browser side. For developers and site operators, every day these issues go undiscovered, the attack surface keeps growing.

Enterprise-grade DLP solutions on the market are heavy to deploy and expensive, while purely manual checks cannot keep up with the daily pace. Hx0 DataGuard is built to fill this gap — **putting "page exposure detection" and "input leak prevention" right inside the browser: ready out of the box, running locally, check anytime.**

---

## What Problems It Solves

| Pain point | How Hx0 DataGuard handles it |
|------|-------------------|
| Accidentally pasting keys, connection strings, or internal documents into AI chats | **Input leak prevention** automatically detects and reminds/blocks before sending — no manual redaction needed |
| Plaintext keys or sensitive data hidden in the frontend pages of authorized websites | **Page sensitive data detection** scans the DOM and scripts with one click, showing match context |
| External JS exposing APIs, admin endpoints, or intranet paths that should not be public | **API detection** extracts path assets to help shrink the site's exposure surface |
| Emails spoofing organizational identity, hiding real redirects, or carrying suspicious attachments | **Phishing email detection** analyzes webmail and EML files offline, outputting risk evidence, authentication summaries, and IOC classification |
| Scan results hard to retain and hand over for fixing | **Report export** generates HTML / Markdown / JSON for reporting and follow-up |
| Worry that detection tools upload page content to the cloud | **Local-first computation** — scan data stays on your machine, no account registration required |

> **Note**: The output of this tool is for auxiliary assessment and security self-checks only. It **cannot replace** formal penetration testing, code audits, or compliance conclusions.

---

## New User Benefits

**Get a 1-day trial VIP membership on first install**, with all features fully unlocked — no account registration required.

After the trial ends, you can subscribe in the extension's "Settings" to keep using it. Before subscribing, **back up your User ID immediately** — in the no-registration model, it is the only credential for recovering your membership benefits.

---

## Core Features

| Feature | What it does |
|------|------|
| **Input leak prevention** | Before you type or paste content and hit send, it automatically detects phone numbers, keys, tokens, ID numbers, and other sensitive information — reminding or blocking to prevent accidental sends to AI chats, forms, and chat boxes |
| **Page sensitive data detection** | Scans the current page's DOM, scripts, and comments to find sensitive data exposed in plaintext, showing match locations and context for manual review |
| **API detection** | Extracts API paths, webhooks, intranet addresses, and other endpoint assets from pages and external JavaScript, uncovering endpoint clues that should not appear in the frontend, with optional further probing and verification |
| **Phishing email detection** | Fully offline analysis of webmail, EML downloads, and manually imported files — checking identity authentication, link redirects, phishing frameworks, social engineering language, and attachment structure, with an explainable report |
| **Rule center** | 130 built-in sensitive data rules, with customization, category toggles, and import/export — flexibly adjust the detection scope to your team's standards |
| **Report export** | Organize scan and match results into HTML, Markdown, or JSON reports for retention, reporting, or handing to developers for fixing |

---

## Typical Use Cases

### Preventing accidental leaks of sensitive information when chatting with AI

In daily work, many people paste log snippets, configuration files, and customer data directly into AI chat boxes like ChatGPT, ERNIE Bot, and Doubao. When things get busy, it's easy to **miss an API key, database connection string, phone number, or internal document mixed in** — and one click of "send" causes a data leak.

Manual redaction is also tedious: check section by section, replace, paste again — **time-consuming, laborious, and easy to miss a line**. Hx0 DataGuard's **input leak prevention** automatically scans content after you type or paste, before sending:

- When sensitive information is found, a **top-right reminder** pops up by default, letting you confirm whether to continue
- After checking **"Block"** for a rule in the Rule Center, a **centered modal** intercepts the send
- Recognition is optimized for popular AI sites, ready to use out of the box; input boxes on other web pages are covered as well

> To enable: turn on "Input & send monitoring" and "Clipboard paste monitoring" in the extension popup, and choose the reminder & blocking strength (Light / Standard / Strict) in the sidebar "Settings". **Only enabled rules** participate in detection.

---

### Auditing sensitive information and API exposure on authorized websites during security testing

For security testers, frontend pages and external scripts often hide **information that should not be public**: debug endpoints, admin panel paths, hardcoded tokens, test accounts, or API addresses that should never appear on the browser side. All of these expand the site's attack surface and increase the risk of exploitation.

Within your **authorized** testing scope, Hx0 DataGuard helps you quickly complete a round of exposure auditing right in the browser:

1. Open the target page and click "Scan current page for sensitive info and APIs"
2. Review **page sensitive data** hits in the sidebar — e.g., plaintext keys, phone numbers, ID numbers
3. In **API detection**, review the path assets extracted from scripts — e.g., endpoints to be tested such as `/api/admin/` and `/internal/debug`
4. After review, export a report as fix recommendations for developers or the client

This way, without building a complex toolchain, you can **find unnecessary exposure points on authorized websites faster**, helping sites reduce their attack surface and lower security risk.

> Only use scanning and probing capabilities on systems, pages, or cyber ranges where you have testing authorization; hits require manual review to avoid mistaking comment decoys or test samples for real leaks.

---

### Quickly checking pages for "leaked" data during development and debugging

Before launch or during joint debugging, developers and QA engineers can use page scanning for a quick look: has the current page or its referenced scripts accidentally left behind test keys, intranet addresses, or real user data? Finding and fixing issues early is far easier than firefighting after they are scanned in production.

---

## Quick Start

### 1. Download & Installation

#### Option 1: Chrome & Firefox Add-on Stores (Recommended)

The latest version is officially available on the Chrome Web Store — **one-click install with automatic updates**, no manual extraction or developer mode required.

👉 **[Install Hx0 DataGuard from the Chrome Web Store](https://chromewebstore.google.com/detail/hx0-%E6%95%B0%E6%8D%AE%E5%8D%AB%E5%A3%AB/hkhjbfajliglkonhfpkfkkdcdobikfig)**

Version 1.0.3 is officially available on Firefox Add-ons — **one-click install with automatic updates**, no manual extraction or developer mode required.

👉 **[Install Hx0 DataGuard from Firefox Add-ons](https://addons.mozilla.org/zh-CN/firefox/addon/hx0-%E6%95%B0%E6%8D%AE%E5%8D%AB%E5%A3%AB/)**

For the Firefox browser. After installation, pin the extension icon to the toolbar to get started.

#### Option 2: Offline Installer Packages (CRX / XPI)

If you **cannot access the add-on stores** (e.g., in network-restricted environments), download the offline installer from the [Releases](../../releases) page of this repository:

| Browser | Package |
|--------|--------|
| Chrome / Edge / Brave, etc. | `Hx0-DataGuard-chrome-*.crx` |
| Firefox | `Hx0-DataGuard-firefox-*.xpi` |

**Chrome / Edge / Brave, etc. (`.crx`)**

1. Download **`Hx0-DataGuard-chrome-*.crx`** to your local machine
2. Open the extensions management page (Chrome: `chrome://extensions`, Edge: `edge://extensions`, Brave: `brave://extensions`)
3. Enable **"Developer mode"** in the top-right corner
4. **Drag** the `.crx` file into the extensions management page
5. Click **"Add extension"** in the popup to complete the installation

**Firefox (`.xpi`)**

1. Download **`Hx0-DataGuard-firefox-*.xpi`** to your local machine
2. Open Firefox and enter `about:addons` in the address bar to open the Add-ons Manager
3. Click the **gear icon** in the top-right corner → **"Install Add-on From File…"**
4. Select the downloaded `.xpi` file and confirm the installation as prompted

> You can also drag the `.xpi` file directly into the Firefox window to trigger installation.  
> Offline installations do not auto-update; when a new version is released, please re-download the package from Releases, or switch to the store version.

#### Firefox Version

The Firefox version has been submitted to **AMO (Firefox Add-ons)** for review and **will be available soon**. Once approved, the store link will be updated in this README and in [Releases](../../releases); in the meantime, you can try it via the **`.xpi`** offline installer from Releases.

> After installation, pin the extension icon to the toolbar for daily use.

### 2. First Launch

1. Click the toolbar icon, then read and agree to the User Agreement & Privacy Policy
2. If the interface shows a **User ID**, copy and save it immediately
3. New users automatically receive a **1-day trial VIP** with full access to all features

### 3. Scan the Current Page

1. Open the web page you want to check
2. Click the extension icon and confirm the current site is correct
3. Click "Scan current page for sensitive info and APIs"
4. Open the **sidebar** (via the menu next to the icon or the browser sidebar button), and view results on pages such as "Overview", "Page Sensitive Data", and "API Detection"

### 4. Enable Input Leak Prevention

In the extension **popup**:

- Turn on "**Input & send monitoring**" — the master switch, covering input boxes on any web page (except login pages)
- Optionally turn on "**Clipboard paste monitoring**" — confirms sensitive content before pasting

In the sidebar "**Settings**", you can adjust the reminder & blocking strength: **Light** (enabled high-risk rules), **Standard** (enabled high- + medium-risk rules, default), **Strict** (enabled high- + medium- + low-risk rules). All three levels default to top-right reminders; rules with "Block" checked in the Rule Center trigger a centered modal on send. You can add trusted sites to the whitelist; "Do Not Disturb" in the popup silences the current site for 24 hours.

### 5. Export Reports

After scanning, go to the sidebar "**Reports**" page to preview and export HTML, Markdown, or JSON. For important tasks, export and back up promptly.

---

## Membership

Hx0 DataGuard is **paid software**; full functionality requires a VIP membership.

| Item | Details |
|------|------|
| New user benefit | **1-day trial VIP** on first install |
| How to subscribe | Sidebar or popup → "Settings" → "Become a member" |
| User ID | No registration needed; the User ID shown in the interface is your membership credential — **be sure to back it up after subscribing** |
| Benefit recovery | If your ID is lost, contact customer support via the email below, providing your old ID and payment proof |

---

## FAQ

**No scan results?**  
Make sure the current page actually has scannable content; some external scripts may be skipped due to permissions or timeouts, but the scan results for the page itself are kept.

**Input leak prevention not working?**  
Check whether "Input & send monitoring" is enabled in the popup, and whether the current site is on the whitelist or in Do Not Disturb.

**Can't recover membership after reinstalling?**  
Contact customer support with the User ID you backed up at installation; recovery may not be possible if you cannot provide the old ID.

**When will the Firefox version be available?**  
The Firefox version has been submitted to the AMO store for review; links will be updated in this README and in Releases once approved. Please wait patiently for the official release.

---

## Feedback & Support

- **Issue reports**: [Submit an Issue](../../issues)
- **Official email**: hx0studio@foxmail.com
- **User manual**: after installation, see "Settings → User Manual" in the extension for full documentation
- **Legal & privacy**: after installation, see "Settings → User Agreement & Privacy Policy" in the extension
