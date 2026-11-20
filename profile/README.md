<div align="center">

<img src="https://raw.githubusercontent.com/ci-doctor/.github/main/profile/ci-doctor-logo-dark.svg" width="400" alt="ci-doctor" />

**Root-cause analysis for CI/CD.**

[Docs](https://docs.cidoc.dev) · [Get started](https://docs.cidoc.dev/start/) · [Matchers](https://matchers.cidoc.dev) · [support@cidoc.dev](mailto:support@cidoc.dev)

</div>

---

## The idea

A pipeline fails, and someone opens a 40,000-line log to find the one line that
matters. Hand that log to a model and it blames whatever looks loudest: a missing
cache, a runner warning.

ci-doctor runs when a pipeline fails. Deterministic code decides **where** the job
broke (which phase, which step); only then does a model, if you configure one, explain
**why**, from evidence that open, tested matchers pick out of the log. You get a
verdict a person, a script or a coding agent can act on.

- **Read-only.** It never touches your code, and once analysis starts it exits `0`, so it
  can't change your pipeline's outcome. Only a broken setup exits `1`.
- **Useful with no LLM**, and with any: OpenAI-compatible (self-hosted too), Anthropic,
  Azure, Bedrock, Google, Groq, Mistral, Cohere, xAI.
- **Air-gap friendly.** No telemetry; the matcher registry can be a local copy.
- **GitHub Actions and GitLab CI**, from one provider-neutral core.
- **For coding agents too:** `ci-doctor mcp` serves the same diagnosis over MCP.

ci-doctor is in **beta**.

## What's here

| Repo | What it is |
|------|------------|
| [**ci-doctor**](https://github.com/ci-doctor/ci-doctor) | The analyzer, the GitHub Action, the CLI and the MCP server, plus the docs at [docs.cidoc.dev](https://docs.cidoc.dev). |
| [**matchers**](https://github.com/ci-doctor/matchers) | The official matcher registry: the rules that know what a failure looks like in each tool, each proven on real logs. Catalogue at [matchers.cidoc.dev](https://matchers.cidoc.dev). |

## Try it

**GitHub Actions**, on a workflow triggered by `workflow_run`
([guide](https://docs.cidoc.dev/cicd/github/)):

```yaml
- uses: ci-doctor/ci-doctor@v0.0.1b1
```

**GitLab CI**, as a `.post` job that runs `when: on_failure`, with the image
`docker.io/fennet/ci-doctor:0.0.1b1` ([guide](https://docs.cidoc.dev/cicd/gitlab/)).

**Anywhere else:** `pip install ci-doctorr` (two r's) and `ci-doctor analyze`
([install](https://docs.cidoc.dev/start/install/)).

## Get involved

- **Bugs, wrong diagnoses and ideas:** open an issue on [ci-doctor](https://github.com/ci-doctor/ci-doctor/issues/new/choose).
- **A matcher for your tool, or one that misfires:** open an issue on [matchers](https://github.com/ci-doctor/matchers/issues/new/choose).
- **Contribute:** each repo's `CONTRIBUTING.md`.
- **Anything else:** [support@cidoc.dev](mailto:support@cidoc.dev)
