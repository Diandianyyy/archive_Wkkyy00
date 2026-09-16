# Wkkyy00 APT repository archive

This repository incrementally archives packages published at
<https://wkkyy00.github.io/>.

The scheduled GitHub Actions workflow runs hourly. It compares SHA-256 hashes
from the upstream `Packages` index with the local index, downloads only missing
packages, verifies each download, and rebuilds the local indexes. Existing
packages are never removed when they disappear upstream.

The initial upstream snapshot contains 1,705 entries and 1,704 unique package
hashes (about 3.73 GB). Scheduled runs download up to 100 missing packages.
A manual run with `max_downloads: 0` drains the backlog, committing and pushing
each batch of 100 packages so progress is preserved between batches.

APT source: <https://diandianyyy.github.io/archive_Wkkyy00/>

GitHub Pages uses GitHub Actions deployment. Each successful sync publishes a
small site containing indexes; package URLs point to this backup repository
at the corresponding commit. This avoids putting the multi-gigabyte package
collection into a Pages deployment. No upstream download is needed to install
an archived package. This archives indexed APT packages, not all Git history.
