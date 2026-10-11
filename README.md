# Wirecall

Support, documentation and legal documents for **Wirecall**, a local HTTP API client for
VS Code.

**This repository holds no source code.** It gives Wirecall a public issue tracker and a home
for its documentation.

- **Download:** the current package is on the [Releases page](../../releases/latest).
- **Report a bug or ask for a feature:** [open an issue](../../issues), or email
  support.zuhaib@gmail.com.

---

## What Wirecall does

Keep your requests yours. Wirecall sends HTTP requests from inside VS Code and keeps your
collections on your own machine.

Free, including commercial use:

- Local requests with parameters, headers, authentication and a body.
- Named collections, request history and environments with `{{variable}}` references.
- Import from Postman v2.1, Thunder Client v1.1 and v1.2 collections and Bruno HTTP request
  files. Export to Wirecall JSON.
- Credentials and marked environment secrets are kept in VS Code SecretStorage.

Pro and Team add:

- Sequential collection runs with status, body and JSON assertions.
- JSON and JUnit reports.
- A headless CI command.
- Shared environment definition files, with each secret supplied locally.

## Getting started

1. Install Wirecall. To install the package from the Releases page, open the Extensions view in
   VS Code, open the **...** menu and choose **Install from VSIX**.
2. Open the Command Palette and select **Wirecall: Open API Client**.
3. Enter an HTTP or HTTPS URL and select **Send**.
4. Use **Save request** to keep a request in the selected collection.
5. **Edit environments** adds a public or secret variable. Use `{{variable}}` in requests.

For response checks in a Pro run, enter one line per check: `status: 200`,
`contains: accepted` or `json $.count: 2`. A run without explicit checks expects a 2xx status.

## Headless CI

The installed extension includes `dist/cli.cjs`, which needs Node.js 20 or later.

1. Save the licence key in your CI secret store as `WIRECALL_LICENSE_KEY`.
2. Run `node dist/cli.cjs activate` once and save the returned `WIRECALL_INSTALL_UID` and
   `WIRECALL_INSTALL_ID` beside the key.
3. Run `node dist/cli.cjs run collection.json --env environment.json --json result.json --junit result.xml`.
4. Bind marked secrets with `WIRECALL_VAR_<variable_name>` in the CI secret store.

Exit code 0 means every check passed, 1 means a failed or cancelled run, and 2 means invalid
input or a licence refusal. Run `node dist/cli.cjs deactivate` before retiring a CI machine.

## Requirements and limits

- VS Code 1.95 or later, on the desktop, in a remote host or in the browser.
- Browser hosts need the API to allow CORS. Desktop and remote hosts connect directly.
- Redirects are refused, so use the destination URL. TLS certificates are always verified.
- Request bodies up to 1 MB, responses up to 5 MB, 30 seconds of network time per request.
- History keeps the latest 500 request templates. Responses are shown in memory only.
- Imports accept up to 5 MB and 5,000 requests per file. Scripts and non-raw bodies are left
  out of an import.

## Pricing

Free local features stay free, including for commercial work.

| Plan | Monthly | Annual |
| --- | ---: | ---: |
| Pro | USD 5 per seat | USD 48 per seat |
| Team | USD 9 per seat | USD 84 per seat |

Every plan starts with a free 14-day trial and no payment method. Select
**Start 14-day Pro trial** in Wirecall, then activate the key with **Manage license**.
Freemius handles checkout, receipts, renewals, cancellation and refunds.

## Refunds

A purchase can be refunded within 30 days if Wirecall does not work for you. Email
support.zuhaib@gmail.com with the email address used at checkout. Cancelling a subscription
stops future renewals, and the free local features keep working.

## Privacy

Wirecall has no analytics and no cloud sync. Your collections stay in VS Code's local storage.
API requests go only to the addresses you enter. Licence actions contact Freemius with the
licence key and an installation identifier. The full policy is in [PRIVACY.md](PRIVACY.md).

## Support

Open an issue here or email support.zuhaib@gmail.com. Include the Wirecall version, the VS Code
version, whether you use the desktop or the browser, the steps that show the problem and the
error text. **Remove credentials, private URLs and response data from anything you paste.**
A licence key, password or API token is never needed.

## Legal

- [Licence terms](EULA.md)
- [Privacy policy](PRIVACY.md)

Third-party licences ship inside the extension package. Wirecall itself is proprietary; this
repository is for support and documentation only.
