# Changelog

## 1.1.1 - 2026-11-22
- `cddd/app-cddd.py` inside `cddd.zip` updated to the version of VEGA-python-models commit 3af8015: it reads the
  trained model from the `default_model` folder next to the script, where the zip extracts it, and falls back to the
  default location of the cddd library (appdirs) when that folder is missing. VEGA Core can then keep every CDDD file
  in its own folder; Core releases up to 1.3.24, which move the model to the library location, keep working through
  the fallback. Descriptors are byte-identical. All other entries of the zip are unchanged.

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
