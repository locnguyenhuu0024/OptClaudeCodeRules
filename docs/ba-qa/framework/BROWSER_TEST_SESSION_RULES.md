# BROWSER_TEST_SESSION_RULES — Claude in Chrome UI testing

## Purpose and authority

For a QA-Handoff UI test, reduce redundant **conversational** confirmations without overriding Claude Code or Claude in Chrome permission enforcement. These instructions cannot approve Chrome actions or change the user's tool/site permission settings.

Load only when performing a browser UI test with Claude in Chrome. Keep filesystem outputs in the existing flat project-workspace/work/ and project-workspace/tests/ directories. Do not create subfolders or reorganize existing files.

## One scoped test-session agreement

Before executing, derive the following from the user's QA-Handoff and other trusted instructions:
- Target **test/staging website origins**, and explicitly authorized additional origins (if any).
- Target features, expected results, test case IDs, data/fixtures, and allowed browser actions.
- Test account/role, environment, safe side effects and any prohibited workflows.
- Appropriate evidence locations in the two existing flat workspace folders.

If the necessary authorization is absent or ambiguous, obtain **one concise scope clarification before starting**. Never invent a test URL, permission, or approved side effect. Consent to an overall test plan is not consent to a sensitive or prohibited action.

When the test session is scoped and the relevant browser/tool permissions are granted, perform ordinary in-scope browser steps continuously, e.g. reading pages, scrolling, navigating approved test origins, clicking controls, entering **non-sensitive fake test data**, checking validation/errors and taking permitted screenshots. **Do not ask the user before each individual click, input, scroll, tab change or page transition.** Reuse the authorized scope during the active test instead of repeatedly requesting conversational permission.

This is a behavior guideline, NOT a grant of browser permissions. If Claude Code/extension displays a real approval prompt, do not bypass, simulate, suppress or answer it; the user must approve in the product UI. If a test crosses to an unapproved origin, requires new credentials, alters access controls, enters sensitive data, downloads, makes external communications/financial transactions, changes production data or triggers other significant effects, stop and request the appropriate approval or mark BLOCKED. Some actions are platform-prohibited regardless of approval. CAPTCHA/login challenges must be handled by the user as required by the integration.

## Configuration for the user (not an agent action)

1. In Claude Code run /chrome to verify extension connection and site permission status.
2. Execute UI tests outside **Plan Mode**. In Plan Mode state-changing browser calls prompt for approval even if reading is allowed.
3. Open Claude in Chrome extension > ... > Extension settings > Permissions. On a trusted staging/test origin choose **Always allow actions on this site** when a site permission prompt is presented; **Allow this action** only covers one action. Grant only to trusted test domains, not unrelated production sites.
4. If the extension/side panel exposes its approval mode, **Automatically approve** reduces repetitive questions while retaining safety checks. Do NOT recommend Skip all approvals for normal QA.
5. Use /permissions in Claude Code to inspect Ask/Allow/Deny rules. An explicit Ask overrides Allow. Do not change settings automatically or add broad allowlists for all browser/MCP tools.
6. Chrome extension may still require explicit permissions for sensitive input, authorization changes, downloads and protected sites, irrespective of these rules.

## Roles

The Chrome-capable **main session** performs browser tool calls when its integration is available. The specialized QA agents (which may have restricted tool lists) can prepare scenarios or interpret returned evidence; do not claim they can independently operate Chrome if the tool is not exposed to them. Preserve explicit model/effort routing; do not change main model to address permissions.

## Honest execution and diagnostics

Record each actual test's TC/AC reference, environment/URL, tested actions, observable expected/actual, evidence reference and PASS/FAIL/BLOCKED/NOT_RUN. No fake PASS for a denied action. If prompts recur, identify the responsible layer:
- conversational question: redundant internal clarification; apply scoped agreement;
- Claude Code permission prompt: /permissions and session mode;
- Chrome site permission prompt: site-specific allow/approval;
- protected action, login or CAPTCHA: user action required.

Never advise bypassing safety checks through scripts or alternative tools solely to avoid approval.

## Official docs
- https://code.claude.com/docs/en/chrome
- https://code.claude.com/docs/en/permissions
- https://support.claude.com/en/articles/12902446-claude-in-chrome-permissions-guide
