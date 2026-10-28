# VERIFY — ai0S-still (signed-only-no-anchor)

Independent verification guide for the `ai0S-still` bundle ("BELOW" — Novella + Realization Workbook + `.0s` Protocol).

- **Mode:** `signed-only-no-anchor` (Ed25519 signatures + SHA-256 manifest + parent chain to `ai0S-deepdive-2` and `PID 1`, without OTS/TSA blockchain round)
- **Signer (Ed25519):** `9F4D9A266D720FE6336574D87B410637560297CF` (`Marcus Dilger <private@privacy.law>`)
- **Origin Anchor (`PID 1`):** `ai0S@sha256:b3aeee619d9cb691cc6618466407d56598e830c53c6d024748d4582887c57d13`
- **Parent Anchor (`Series II`):** `ai0S-deepdive-2@sha256:a0a48ed5fc069ca83a33df39b767ced22b5f6cff4ac36d0c65be699940fef19a`
- **Bundle Root (`SHA256(ROOT.preimage)`):** `b757b360827b0e28a577d0ec73c6cfe916b0e6baca340feedb6d56c7085883c3`

---

## 1. Import Public Key

```bash
gpg --import pubkey.asc
gpg --fingerprint 9F4D9A266D720FE6336574D87B410637560297CF
```

## 2. Verify Manifest & File Signatures

```bash
gpg --verify MANIFEST.json.sig MANIFEST.json
for s in *.0s.sig NOVELLE-*.md.sig NOVELLA-*.md.sig WERKBUCH-*.md.sig WORKBOOK-*.md.sig README.md.sig; do
  gpg --verify "$s" "${s%.sig}"
done
```

## 3. Verify SHA-256 Checksums Against `MANIFEST.json`

```bash
jq -r '.files[] | "\(.sha256)  \(.path)"' MANIFEST.json | sha256sum -c -
```

## 4. Verify `ROOT.preimage` Hash

```bash
cat MANIFEST.json MANIFEST.json.sig | sha256sum
sha256sum ROOT.preimage
# Expected: b757b360827b0e28a577d0ec73c6cfe916b0e6baca340feedb6d56c7085883c3
```
