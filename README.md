# VietGrid Updates

## Tải bản thử VietGrid

**[Mở trang Release và danh sách Assets](https://github.com/thangnguyenquoc2776/vietgrid-updates/releases/tag/office-4247e6406da8f35a00e286e2c4c17984223d26668d7c7f3d4e0ad70a884f60cd)** · **[Tải gói cập nhật VietGrid-native-1.zip](https://github.com/thangnguyenquoc2776/vietgrid-updates/releases/download/office-4247e6406da8f35a00e286e2c4c17984223d26668d7c7f3d4e0ad70a884f60cd/VietGrid-native-1.zip)**

Bản Preview cho **OneNote 16.0.20527.20196, Windows x64**. Đây là gói cập nhật native dành cho bản VietGrid đã cài phù hợp; chưa phải bộ cài đầy đủ cho máy mới. Trong trang Release, mở **Assets** để xem ZIP, metadata đã ký, khóa public và thông báo bản quyền (5 tệp đính kèm). Tab Code hiện chỉ có README; tệp phát hành được lưu trong Releases.

---

Signed native compatibility updates for OneNote desktop on Windows x64.

The automatic updater was deployed and tested on one machine on 2026-11-15: public GitHub download, pinned RSA-3072/SHA-256 signature, asset hashes, backup, same-payload installation and normal OneNote reopening. The user confirmed grid auto-start, no cleaning-up dialog and normal data/sync.

As of 2026-11-16, the five-minute timer has been removed. A native watcher checks the Office fingerprint once at logon and then waits for Windows file-change notifications for onmain.DLL; it invokes the updater only for a build mismatch. If no compatible release is available, it does not poll GitHub periodically. It applies a compatible signed package only when OneNote and owned helpers are closed. It never forces OneNote to close. Runtime policy and sandbox binding remain local to each machine.

Each release tag is office-<onmain.DLL SHA-256>. Assets are release.json, release.sig, the ZIP, the public signing key and third-party notices. Existing clients keep their pinned key; they do not trust a replacement key downloaded from the feed.

**Future Office builds still need a verified compatible release to be published.** GitHub does not invent patches. Unknown builds remain blocked; changes to the frontend or ABI may require a full installer. A successful same-payload test does not prove compatibility with future Office builds or other machines.

No Office DLL/PDB, notebooks, backups, sandbox IDs or private signing keys are published. The private release key stays in the Windows certificate store on the maintainer machine. MinHook/HDE license notices accompany the release and signed metadata.