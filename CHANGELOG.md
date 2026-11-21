# Changelog

## 1.1.0 - 2026-11-21
- `cddd/app-cddd.py` inside `cddd.zip` updated to the version of VEGA-python-models commit 90be04e: it fills the
  encoder tensor up to a multiple of 128 rows, which makes the CDDD descriptors reproducible between processes.
  1.0.0 still carried the older script, so every fresh extraction ran without the fix. All other entries of the zip
  are unchanged. Published on Nexus `protoqsar-maven-releases`.
- Installations that already extracted CDDD keep their own copy of the script: extraction happens only when the
  CDDD folders are missing.

## 1.0.0 - 2026-11-21
- Serialized CDDD model `descriptor/cddd.zip`, moved here unchanged (byte-identical) from VEGA Core 1.3.23.
  Published on Nexus `protoqsar-maven-releases`.
