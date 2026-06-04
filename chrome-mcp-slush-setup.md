---
marp: true
paginate: true
footer: "Sui"
---

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');

section {
  background: #000000;
  color: #8B8B8B;
  font-family: 'Inter', 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
  font-size: 22px;
  font-weight: 400;
  line-height: 1.5;
  padding: 60px;
  width: 1280px;
  height: 720px;
  position: relative;
}

section h1 { color: #FFFFFF; font-size: 42px; font-weight: 700; line-height: 1.15; margin: 0 0 16px 0; letter-spacing: -0.02em; }
section h2 { color: #FFFFFF; font-size: 32px; font-weight: 600; line-height: 1.25; margin: 0 0 12px 0; }
section h3 { color: #FFFFFF; font-size: 24px; font-weight: 600; line-height: 1.3; margin: 0 0 8px 0; }
section h4 { color: #8B8B8B; font-size: 20px; font-weight: 500; line-height: 1.4; margin: 0 0 8px 0; }
section p { margin: 0 0 12px 0; }
section strong { color: #FFFFFF; font-weight: 600; }
section em { color: #4DA2FF; font-style: normal; }
section a { color: #4DA2FF; text-decoration: none; }
section code { background: #1A1A1A; color: #4DA2FF; padding: 2px 6px; border-radius: 4px; font-size: 0.9em; }
section pre { background: #0A0A0A; border: 1px solid #3A3A3A; border-radius: 8px; padding: 14px 18px; margin: 10px 0; }
section pre code { background: transparent; padding: 0; font-size: 0.82em; }
section ul, section ol { margin: 0 0 12px 0; padding-left: 24px; }
section li { margin-bottom: 6px; }
section li::marker { color: #4DA2FF; }
section blockquote { border-left: 3px solid #4DA2FF; padding-left: 16px; margin: 12px 0; color: #AAAAAA; }
section hr { border: none; border-top: 1px dashed #3A3A3A; margin: 24px 0; }

section::after { color: #FFFFFF; font-size: 12px; font-weight: 600; background: #4DA2FF; border-radius: 2px; padding: 2px 8px; }
section footer { color: #8B8B8B; font-size: 14px; position: absolute; bottom: 24px; left: 60px; }
section footer::before { content: ''; display: inline-block; width: 14px; height: 18px; background: url("data:image/svg+xml,%3Csvg width='300' height='384' viewBox='0 0 300 384' fill='none' xmlns='http://www.w3.org/2000/svg'%3E %3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M240.057 159.914C255.698 179.553 265.052 204.39 265.052 231.407C265.052 258.424 255.414 284.019 239.362 303.768L237.971 305.475L237.608 303.31C237.292 301.477 236.929 299.613 236.502 297.749C228.46 262.421 202.265 232.134 159.148 207.597C130.029 191.071 113.361 171.195 108.985 148.586C106.157 133.972 108.258 119.294 112.318 106.717C116.379 94.1569 122.414 83.6187 127.549 77.2831L144.328 56.7754C147.267 53.1731 152.781 53.1731 155.719 56.7754L240.073 159.914H240.057ZM266.584 139.422L154.155 1.96703C152.007 -0.655678 147.993 -0.655678 145.845 1.96703L33.4316 139.422L33.0683 139.881C12.3868 165.555 0 198.181 0 233.698C0 316.408 67.1635 383.461 150 383.461C232.837 383.461 300 316.408 300 233.698C300 198.181 287.613 165.555 266.932 139.896L266.568 139.438L266.584 139.422ZM60.3381 159.472L70.3866 147.164L70.6868 149.439C70.9237 151.24 71.2239 153.041 71.5715 154.858C78.0809 189.001 101.322 217.456 140.173 239.496C173.952 258.724 193.622 280.828 199.278 305.064C201.648 315.176 202.059 325.129 201.032 333.835L200.969 334.372L200.479 334.609C185.233 342.05 168.09 346.237 149.984 346.237C86.4546 346.237 34.9484 294.826 34.9484 231.391C34.9484 204.153 44.4439 179.142 60.3065 159.44L60.3381 159.472Z' fill='%234DA2FF'/%3E %3C/svg%3E") no-repeat center/contain; margin-right: 5px; vertical-align: middle; }
section header { color: #4DA2FF; font-size: 14px; font-weight: 500; position: absolute; top: 24px; right: 60px; }

section .grid { display: grid; gap: 24px; width: 100%; height: auto; }
section .col { display: flex; flex-direction: column; border-top: 1px dashed #3A3A3A; padding-top: 16px; }
section .col h3 { margin-bottom: 8px; }
section .col p { font-size: 18px; margin: 0; }

section .category { display: inline-flex; align-items: center; gap: 6px; font-size: 11px; font-weight: 600; letter-spacing: 0.08em; text-transform: uppercase; color: #8B8B8B; font-family: 'Inter', monospace; margin-bottom: 8px; }
section .category::before { content: ''; display: inline-block; width: 8px; height: 8px; background: #4DA2FF; flex-shrink: 0; }

section .col.icon-marker h3::before { content: ''; width: 20px; height: 20px; margin-right: 8px; background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none'%3E%3Cpath d='M12 2C12 2 5 10 5 14.5C5 18.09 8.13 21 12 21C15.87 21 19 18.09 19 14.5C19 10 12 2 12 2Z' stroke='%234DA2FF' stroke-width='1.5' fill='none'/%3E%3Cpath d='M12 18C14.21 18 16 16.21 16 14C16 11 12 6 12 6C12 6 8 11 8 14C8 16.21 9.79 18 12 18Z' stroke='%234DA2FF' stroke-width='1' fill='none'/%3E%3C/svg%3E"); background-size: contain; background-repeat: no-repeat; }

section .card { background: #0A0A0A; border: 1px solid #1A1A1A; border-radius: 8px; padding: 14px 18px; margin-bottom: 8px; }
section .card h4 { color: #FFFFFF; margin: 0 0 4px 0; }
section .card p { margin: 0; font-size: 16px; }

/* cover-gradient */
section.cover-gradient { display: flex; flex-direction: column; justify-content: flex-start; padding-top: 60px; color: #FFFFFF; background: linear-gradient(135deg, #0C1F3F 0%, #1040A0 60%, #4DA2FF 100%); }
section.cover-gradient h1 { font-size: 56px; font-weight: 700; color: #FFFFFF; letter-spacing: -0.03em; margin-bottom: 16px; position: relative; z-index: 1; }
section.cover-gradient p { font-size: 22px; color: rgba(255,255,255,0.85); max-width: 60%; position: relative; z-index: 1; }
section.cover-gradient footer { display: none; }
section.cover-gradient::after { display: block; content: ''; position: absolute; bottom: 40px; right: 60px; width: 140px; height: 55px; background: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 220 80'%3E%3Cg transform='translate(0,2) scale(0.19)'%3E%3Cpath fill-rule='evenodd' clip-rule='evenodd' d='M240.057 159.914C255.698 179.553 265.052 204.39 265.052 231.407C265.052 258.424 255.414 284.019 239.362 303.768L237.971 305.475L237.608 303.31C237.292 301.477 236.929 299.613 236.502 297.749C228.46 262.421 202.265 232.134 159.148 207.597C130.029 191.071 113.361 171.195 108.985 148.586C106.157 133.972 108.258 119.294 112.318 106.717C116.379 94.1569 122.414 83.6187 127.549 77.2831L144.328 56.7754C147.267 53.1731 152.781 53.1731 155.719 56.7754L240.073 159.914H240.057ZM266.584 139.422L154.155 1.96703C152.007-0.655678 147.993-0.655678 145.845 1.96703L33.4316 139.422L33.0683 139.881C12.3868 165.555 0 198.181 0 233.698C0 316.408 67.1635 383.461 150 383.461C232.837 383.461 300 316.408 300 233.698C300 198.181 287.613 165.555 266.932 139.896L266.568 139.438L266.584 139.422ZM60.3381 159.472L70.3866 147.164L70.6868 149.439C70.9237 151.24 71.2239 153.041 71.5715 154.858C78.0809 189.001 101.322 217.456 140.173 239.496C173.952 258.724 193.622 280.828 199.278 305.064C201.648 315.176 202.059 325.129 201.032 333.835L200.969 334.372L200.479 334.609C185.233 342.05 168.09 346.237 149.984 346.237C86.4546 346.237 34.9484 294.826 34.9484 231.391C34.9484 204.153 44.4439 179.142 60.3065 159.44L60.3381 159.472Z' fill='white'/%3E%3C/g%3E%3Ctext x='72' y='57' font-family='Inter,sans-serif' font-size='52' font-weight='400' fill='white'%3ESui%3C/text%3E%3C/svg%3E") no-repeat center/contain; z-index: 1; }

/* content */
section.content { display: flex; flex-direction: column; justify-content: flex-start; align-items: flex-start; }
section.content h1 { font-size: 42px; margin-bottom: 16px; }

/* list-right */
section.list-right { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: start; }
section.list-right .content { display: flex; flex-direction: column; justify-content: center; height: 100%; }
section.list-right .cards { display: flex; flex-direction: column; gap: 8px; }

/* cols-2-center */
section.cols-2-center { text-align: center; }
section.cols-2-center h1 { width: 100%; }
section.cols-2-center .grid { grid-template-columns: repeat(2, 1fr); margin-top: 24px; text-align: left; }

/* cols-3 */
section.cols-3 .grid { grid-template-columns: repeat(3, 1fr); margin-top: 24px; }

/* cols-4-icon */
section.cols-4-icon .grid { grid-template-columns: repeat(4, 1fr); margin-top: 24px; }
section.cols-4-icon .col.icon-marker h3::before { display: inline-block; }
</style>

<!-- =====================================================
     SLIDE 1: Cover
     ===================================================== -->
<!-- _class: cover-gradient -->
<!-- _paginate: false -->

# Sui dApp Test Automation

Mirroring the chrome-devtools-mcp + Slush wallet setup

---

<!-- =====================================================
     SLIDE 2: Prerequisites & one-time setup
     ===================================================== -->
<!-- _class: list-right -->

<div class="content">

# One-time Setup

Three things that must exist before any session:

- Chrome for Testing (separate binary)
- Persistent wallet profile at `~/dev-chrome`
- MCP attach hook in `~/.claude/hooks/`

</div>

<div class="cards">
<div class="card">

#### Chrome for Testing

Download from [googlechromelabs.github.io/chrome-for-testing](https://googlechromelabs.github.io/chrome-for-testing/). Place in `/Applications/`. Separate binary — never conflicts with regular Chrome.

</div>
<div class="card">

#### ~/dev-chrome wallet profile

Create once by launching with `--user-data-dir=$HOME/dev-chrome`. Install **Slush** (`opcgpfmipidbgpenhmajoajpbobppdil`) and MetaMask (`nkbihfbeogaeaoehlefnkodbefgpgknn`), unlock both. Profile persists on disk indefinitely.

</div>
<div class="card">

#### patch-chrome-devtools-mcp.sh (SessionStart hook)

Injects `--browser-url=http://127.0.0.1:9222` into the installed plugin's config every session — so MCP attaches to *your* Chrome instead of spawning a fresh wallet-less one. Register in `~/.claude/settings.json` under `hooks.SessionStart`.

</div>
</div>

---

<!-- =====================================================
     SLIDE 3: Launch command
     ===================================================== -->
<!-- _class: content -->

# Launch Chrome on :9222

Kill any existing instance first (prevents profile-lock), then launch the single debuggable wallet Chrome:

```bash
pkill -f "Google Chrome for Testing" 2>/dev/null; sleep 1

"/Applications/Google Chrome for Testing.app/Contents/MacOS/Google Chrome for Testing" \
  --remote-debugging-port=9222 \
  --user-data-dir="$HOME/dev-chrome" \
  > /dev/null 2>&1 &

sleep 2
```

**`--remote-debugging-port=9222`** — exposes the CDP WebSocket endpoint that both chrome-devtools-mcp and `scripts/cdp.py` attach to.

**`--user-data-dir=$HOME/dev-chrome`** — loads your wallet profile (extensions, accounts, unlock state) instead of a throwaway profile.

Kill-first guarantees exactly one Chrome-for-Testing owns the profile *and* holds the debug port.

---

<!-- =====================================================
     SLIDE 4: The two silent failure modes
     ===================================================== -->
<!-- _class: cols-2-center -->

# Two Ways to End Up Without a Wallet

<div class="grid">
<div class="col">

<span class="category">PROFILE-LOCK TRAP</span>

### Chrome owns ~/dev-chrome but without :9222

A second launch can't lock the busy profile and silently falls back to a **fresh, extension-less** profile. The port comes up, MCP attaches, the connect modal is empty.

Detect: `curl 127.0.0.1:9222/json | grep chrome-extension` → no wallet ids

**Fix:** kill the no-port Chrome first, then relaunch.

</div>
<div class="col">

<span class="category">ATTACH TRAP</span>

### MCP spawns its own Chrome instead of attaching

Without `--browser-url`, chrome-devtools-mcp ignores your :9222 instance and opens its own wallet-less Chrome. Two windows appear; `list_pages` succeeds but the dapp's wallet modal is always empty.

Detect: `ps aux | grep "Google Chrome.app" | grep -v "for Testing" | grep "chrome-devtools-mcp"`

**Fix:** run `patch-chrome-devtools-mcp.sh`, restart the MCP connection.

</div>
</div>

---

<!-- =====================================================
     SLIDE 5: Verify before automating
     ===================================================== -->
<!-- _class: cols-3 -->

# Verify Before You Automate

<div class="grid">
<div class="col">

<span class="category">PORT CHECK</span>

### :9222 is up

```bash
curl -sS -m 1 \
  http://127.0.0.1:9222/json/version \
  >/dev/null && echo "up" || echo "down"
```

Necessary but not sufficient — a fallback profile also brings up 9222.

</div>
<div class="col">

<span class="category">EXTENSION CHECK</span>

### Wallet extensions loaded

```bash
curl -s http://127.0.0.1:9222/json \
  | grep -oE 'chrome-extension://(nkbihfbeogaeaoehlefnkodbefgpgknn|opcgpfmipidbgpenhmajoajpbobppdil)' \
  | sort -u
```

At least one line for Slush or MetaMask must appear. Zero lines = profile-lock trap fired.

</div>
<div class="col">

<span class="category">MCP ATTACH CHECK</span>

### MCP is attaching, not spawning

```bash
ps aux \
  | grep "Google Chrome.app" \
  | grep -v "for Testing" \
  | grep "chrome-devtools-mcp"
```

Any output = attach trap active. Run the patch hook and **restart** the MCP server connection (config changes don't hot-reload).

</div>
</div>

---

<!-- =====================================================
     SLIDE 6: Two worlds mental model
     ===================================================== -->
<!-- _class: cols-2-center -->

# Two Worlds, Two Tools

<div class="grid">
<div class="col">

<span class="category">DAPP PAGES — https://…</span>

### chrome-devtools-mcp

`navigate_page` · `take_snapshot` · `click` · `evaluate_script`

Standard MCP tools work on any http(s) page. Use them to click the connect button, drive dapp flows, and verify the post-login state.

</div>
<div class="col">

<span class="category">SLUSH POPUPS — chrome-extension://…</span>

### scripts/cdp.py

`targets` · `inspect` · `click` · `eval`

Extension pages **never appear** in `list_pages`. cdp.py talks raw CDP over the :9222 WebSocket — the only way to reach approval popups. Bundled with the `drive-slush-wallet` skill; zero dependencies (Python stdlib only).

</div>
</div>

---

<!-- =====================================================
     SLIDE 7: Core approval loop
     ===================================================== -->
<!-- _class: cols-4-icon -->

# Driving Every Slush Approval

<div class="grid">
<div class="col icon-marker">

### Discover

```bash
python3 scripts/cdp.py \
  targets opcgpfmi...
```

Find the popup by extension id. The URL hash tells you what's being asked: `#approve-connection`, `#sign-personal-message`, `#approve-transaction`.

</div>
<div class="col icon-marker">

### Inspect

```bash
python3 scripts/cdp.py \
  inspect #approve-connection
```

Prints title, visible body, button labels, and `hasPasswordField`. Always read before clicking — never assume button names.

</div>
<div class="col icon-marker">

### Click

```bash
python3 scripts/cdp.py \
  click <target> "Approve"
```

Matches by trimmed button text (case-insensitive). If no match, available labels are printed so you can retry. Popup closes on resolve.

</div>
<div class="col icon-marker">

### Verify

Back on **chrome-devtools-mcp** — check the dapp reflects the new state via `evaluate_script`. A successful click is not proof; the dapp's updated UI is.

If the popup vanished before the click, it timed out — re-trigger from the dapp and repeat.

</div>
</div>
