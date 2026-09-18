# Red Hat AI Design Handbook

This repository is a generated public distribution of the Red Hat AI Design Handbook.

The canonical source, editorial workflow, and publication policy are maintained in the private UXD GitLab repository. Changes to this repository should be made through the publication pipeline rather than edited directly.

The handbook is exposed to the PatternFly MCP as the `uxd-handbook` collection through `docs.json`.

## Repository policy

This is a read-only public distribution. GitLab is the sole source of truth; content changes must be made there and are published here by CI.

Handbook images are treated as release artifacts. Images in `scripts/public-image-allowlist.json` are published unchanged; new or modified images are automatically excluded until reviewed and added to the allowlist. Their Markdown references are replaced with accessible alt text, so an unknown image cannot block publication or enter the public mirror accidentally.

Pull requests, issues, discussions, and wiki content should remain disabled. The default branch should allow updates only from the handbook publishing identity, with force-pushes and branch deletion blocked.
