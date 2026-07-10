# Clay Seal

Identity and permissions for AI agents, checked at runtime.

An agent should be able to prove which agent it is, show what it is allowed to
do right now, and let the other side verify both without a callback. That is
what Clay Seal builds.

## clayseal-identity

Short-lived, attested credentials for agents. A workload proves where it runs
with real node attestation (a Google instance identity token, a Kubernetes
projected service-account token, or an AWS instance identity document). It
receives a SPIFFE identity as a JWT-SVID, or an X.509-SVID for mTLS, bound to a
key it holds. Alongside the identity it carries a capability token it can narrow
for a single task and hand to a sub-agent. A server verifies all of it offline.

```bash
pip install clayseal-identity
```

Repo: [clayseal/clayseal-identity](https://github.com/clayseal/clayseal-identity)

## @clayseal/verify

The JavaScript verifier for the same credentials. Add it to a Node MCP server or
an OpenClaw tool plugin to check an agent's credential and authorize each tool
call against its capability token. A stolen token without the agent's key
authorizes nothing.

```bash
npm install @clayseal/verify
```

## Links

- Site: [clayseal.com](https://clayseal.com)
- Package: [pypi.org/project/clayseal-identity](https://pypi.org/project/clayseal-identity/)
- Questions: open a discussion on the identity repo
