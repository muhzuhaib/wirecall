# Wirecall privacy

Effective date: 2026-10-10.

Wirecall stores collections, request templates, the latest 500 history entries and public environment values in VS Code's local extension storage. Responses stay in memory and are not saved in history. Recognized authentication credentials, marked environment secrets and the license activation use VS Code SecretStorage. VS Code manages that storage; removing a request does not automatically remove its stored credential.

API requests are sent to the HTTP or HTTPS address you enter, including the parameters, headers, authentication and body you configure. Wirecall follows no redirects and verifies TLS through the host. Browser hosts enforce CORS. Remote extension hosts, when used, execute on the remote machine and keep their local storage there.

License activation, validation and deactivation contact api.freemius.com. They send your license key, a random installation identifier and the installation ID when applicable. Activation labels the installation Wirecall. The billing provider can receive normal network metadata, such as the requesting IP address. The extension sends no collection, API response, workspace path, account email or machine name to the billing service.

The trial button opens Freemius checkout in your browser without attaching your collections, license key or workspace data. Checkout and its customer account have their own privacy terms. Review those terms on Freemius before providing information.

Wirecall has no analytics or collection sync service. It does not add telemetry, crash uploads or a cloud account requirement for free features. VS Code and the marketplaces operate separately under their own policies.

Collection exports replace stored credentials with references. Public URLs, headers and bodies are included. Shared environment definitions contain public values and secret names. Reports contain request names and assertion results, excluding response bodies, URLs and credential values. Review every file before sharing it.

Support information is supplied voluntarily by email. Send redacted examples. Privacy questions and requests concerning information you sent to support can be addressed to support.zuhaib@gmail.com.
