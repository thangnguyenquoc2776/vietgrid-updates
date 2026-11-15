# VietGrid Updates

Signed native compatibility updates for OneNote desktop on Windows x64.

The automatic updater was deployed and tested on one machine on 2026-11-15: public GitHub download, pinned RSA-3072/SHA-256 signature, asset hashes, backup, same-payload installation and normal OneNote reopening. The user confirmed grid auto-start, no cleaning-up dialog and normal data/sync.

The installed task checks at logon and every five minutes. It applies a compatible signed package only when OneNote and owned helpers are closed. It never forces OneNote to close. Runtime policy and sandbox binding remain local to each machine.

Each release tag is office-<onmain.DLL SHA-256>. Assets are release.json, release.sig, the ZIP, the public signing key and third-party notices. Existing clients keep their pinned key; they do not trust a replacement key downloaded from the feed.

**Future Office builds still need a verified compatible release to be published.** GitHub does not invent patches. Unknown builds remain blocked; changes to the frontend or ABI may require a full installer. A successful same-payload test does not prove compatibility with future Office builds or other machines.

No Office DLL/PDB, notebooks, backups, sandbox IDs or private signing keys are published. The private release key stays in the Windows certificate store on the maintainer machine. MinHook/HDE license notices accompany the release and signed metadata.