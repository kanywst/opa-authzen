# opa-authzen

**This repository is a pointer. The project lives at
[`kanywst/opa-authzen-plugin`](https://github.com/kanywst/opa-authzen-plugin).**

`opa-authzen` is a nickname people reach for when referring to the OPA
implementation of the
[OpenID AuthZEN Authorization API 1.0][spec]. There is no code here — this repo
exists so that name resolves to something useful instead of a 404.

[spec]: https://openid.net/specs/authorization-api-1_0.html

## What you are probably looking for

| Repository | What it is |
| --- | --- |
| [`opa-authzen-plugin`](https://github.com/kanywst/opa-authzen-plugin) | **OPA-AuthZEN.** An extended OPA that serves the AuthZEN endpoints natively, as an OPA plugin. Start here. |
| [`opa-authzen-interop`](https://github.com/kanywst/opa-authzen-interop) | The AuthZEN interop Todo-scenario PDP built on the plugin, used as its E2E harness. |
| [`mcp-opa-authz`](https://github.com/kanywst/mcp-opa-authz) | The client side. An MCP server that lets an LLM agent ask a real AuthZEN PDP — or evaluate Rego in-process — instead of guessing. |

## Why the name is `-plugin`

It is not a sidecar or a gateway in front of OPA. It registers
`/access/v1/evaluation`, `/access/v1/evaluations`, and
`/.well-known/authzen-configuration` on OPA's *own* HTTP server via OPA's `ExtraRoute`
extension point, so a single OPA process speaks both the Data API and AuthZEN.
The Go module path is `github.com/kanywst/opa-authzen-plugin`, which is why the
repository cannot simply be renamed.

## License

Apache-2.0, matching the plugin.
