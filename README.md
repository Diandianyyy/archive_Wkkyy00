# Wkkyy00 APT repository archive

This repository incrementally archives packages published at
<https://wkkyy00.github.io/>.

The scheduled GitHub Actions workflow runs hourly. It compares SHA-256 hashes
from the upstream `Packages` index with the local index, downloads only missing
packages, verifies each download, and rebuilds the local indexes. Existing
packages are never removed when they disappear upstream.

The initial upstream snapshot contains about 1,705 packages (3.73 GB). The
default batch size is 100 packages, so the first complete backup takes about 18
hourly runs. A manual run can choose another batch size; `0` requests all
missing packages, but a large one-shot run may exceed GitHub Actions limits.

To publish this as an APT source, enable GitHub Pages for the `main` branch and
the repository root after the initial packages have been committed.
