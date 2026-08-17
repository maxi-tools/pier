# Provenance

This repository is a **mirror**, not a fork.

`datacurve-pier` is published to PyPI with no source repository of any kind: no
`home_page`, no `project_urls`, nothing in `pyproject.toml` or `README.md`, and
no matching public repo on GitHub (checked 2026-08-17). There is nothing to fork,
so the contents here are the published sdist, unmodified.

    package   datacurve-pier
    version   0.3.1
    source    https://files.pythonhosted.org/.../datacurve_pier-0.3.1.tar.gz
    license   Apache-2.0 (LICENSE ships in the sdist; PyPI's own metadata field
              says "unstated", which is a packaging omission, not an absence)

## Why mirror it at all

The harness's preflight names `pier` by version, and it was installed on no fleet
box and documented in no repo — so the first person to need it had to rediscover
what it was and where it came from. A pinnable copy under our own org fixes that,
the same way maxi-tools/succinctly, vello_svg, core2 and ockam do for their
upstreams. The difference is only in mechanism: those are forks because their
upstreams are repositories, and this cannot be.

It also makes the dependency surface reviewable. Installing this package pulls in
`daytona`, `modal`, `supabase`, `anthropic` and `litellm` — cloud sandbox and
model providers — as transitive dependencies. The harness pins
`environment_class="docker"` so execution stays local, but the providers land on
disk regardless, and that is worth being able to read rather than infer.

## Rules for this repo

- The initial commit is the pristine 0.3.1 sdist. Do not amend it.
- Local changes go in later commits, so `git diff <initial>..HEAD` is always the
  exact list of our modifications, which Apache-2.0 §4(b) asks us to state.
- Upstream's LICENSE is retained unmodified.
