<div align="center">

<img src="https://raw.githubusercontent.com/ci-doctor/ci-doctor/master/docs/site/public/ci-doctor-icon.svg" width="64" alt="ci-doctor" />

# ci-doctor

**Bringing the agentic loop to CI/CD.**

[Docs](https://docs.cidoc.dev) · [Get started](https://docs.cidoc.dev/start/) · [support@cidoc.dev](mailto:support@cidoc.dev)

</div>

---

## The idea

Coding agents work in a loop: observe, diagnose, act, verify. CI/CD is still
mostly open-loop. A pipeline fails, a human opens a 40,000-line log, scrolls
to find the one line that matters, and guesses at the cause.

We close that loop. When a run fails, ci-doctor reads the evidence, works out
which phase broke and why, separates *your code* from *the infrastructure*,
and hands back a verdict that a person, a script, or another agent can act on.

It is read-only, it never fails your pipeline (always exits `0`), and it
runs where your CI already runs.

## What's here

| Repo | What it is |
|------|------------|
| [**ci-doctor**](https://github.com/ci-doctor/ci-doctor) | The analyzer: failure attribution, phase detection, and the GitHub Action. |
| **matchers** *(soon)* | Community-maintained matcher packs: the rules that know what a failure looks like in each tool. |
| **site** *(soon)* | The website and documentation behind [docs.cidoc.dev](https://docs.cidoc.dev). |

## Try it

```yaml
- uses: ci-doctor/ci-doctor@master
```

Add it to a workflow that triggers on `workflow_run`. See the
[GitHub Actions guide](https://docs.cidoc.dev/cicd/github/).

## Get involved

- **Bugs and ideas:** open an issue on the relevant repo.
- **Contribute:** read each repo's `CONTRIBUTING.md`.
- **Questions or anything else:** [support@cidoc.dev](mailto:support@cidoc.dev)
