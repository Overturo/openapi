> **Release mirror.** This repository is a read-only snapshot of
> `openapi` 2026.09.12.1, published from Overturo's main
> development repository. Issues and pull requests are welcome here; accepted
> changes are ported upstream and appear in the next release snapshot.
> Security reports: see [SECURITY.md](./SECURITY.md).

# Overturo API — OpenAPI document

This repository publishes the OpenAPI 3.1 description of the Overturo REST API
(`openapi.json` and `openapi.yaml`, identical content). The same document is
served live at `https://overturo.com/api/v1/openapi.json`.

## Who governs what

The API is operated and versioned by Overturo's operating companies (OmVi Labs
Inc and Overturo Ltd). This repository, held by Overturo Geneva Association,
publishes **described snapshots** of the supported public contract so that
tooling, third-party SDK authors, and evaluators have a stable, versioned
reference. Publishing a snapshot here does not change the API; the API changes
first, and the next snapshot describes it.

## Versioning

- `info.version` is the API version (currently `v1`).
- Snapshots are tagged by publication date, `vYYYY.MM.DD` (a same-day re-issue
  appends `.N`), and the history is linear: a snapshot is never rewritten.
- The OAuth2 security scheme names the production identity endpoints; regional
  deployments advertise their own in the live document.

## What this snapshot covers

| Figure | Value |
|---|---|
| Paths | 363 |
| Operations | 509 |
| Operations with a typed success schema | 156 |
| Operations with a client method in at least one SDK (`x-overturo-sdks`) | 138 |

An operation's `x-overturo-sdks` lists, per SDK that reaches it, the package a reader installs (`package`) and its public repository (`repository`).
| Operations still on the placeholder success schema (`Empty`) | 353 |
| Operations with a request-body schema | 38 |
| Component schemas | 173 |

Operations on the placeholder schema return a JSON object whose shape is not
yet described; typed schemas are being completed and each snapshot updates the
figures above.

## What this snapshot omits

The served document is the complete route inventory. The published document
omits 6 path(s) that are not part of the supported
partner contract:

- `machine`: 3
- `internal_name`: 3
- `deprecated`: 0

`machine` paths are machine-to-machine surfaces between Overturo regions;
`internal_name` paths are URLs awaiting a public rename and are published once
renamed; `deprecated` paths keep serving existing callers but are no longer
part of the contract.

## Using it

Validate with any OpenAPI 3.1 linter, browse it in an OpenAPI viewer, or
generate a client for a language Overturo does not ship an SDK for. The
first-party SDKs and the shared conformance corpus live in the sibling
repositories of this organization.
