# VegaResources-Cddd

Maven artifact `InSilico:VegaResources-Cddd` holding only the serialized CDDD model
(`src/main/resources/descriptor/cddd.zip`, ~590 MB, stored with Git LFS).

`insilico.core.python.CdddDescriptors` (VEGA Core) reads it from the classpath at `/descriptor/cddd.zip` and
extracts it to the local CDDD folder the first time the descriptors are computed.

It used to live inside the Core; it was moved here so that the Core jar stays small and is not re-deployed and
re-downloaded with 590 MB at every release. Only the model modules that use CDDD descriptors declare it (with
the default compile scope, not `optional`, so that it reaches `VegaModels-All` and the GUI transitively):

- `VegaModels-ApicalCardioTox`, `VegaModels-CardioToxMultitask`, `VegaModels-DiliBayer`,
  `VegaModels-MitochondrialDysfunction` (VEGA-models-human)
- `VegaModels-ONTOX-assay` (VEGA-models-other)

```xml
<dependency>
    <groupId>InSilico</groupId>
    <artifactId>VegaResources-Cddd</artifactId>
    <version>1.0.0</version>
</dependency>
```

Release: `mvn deploy` (Nexus `protoqsar-maven-releases`), then an annotated tag named after the version and a
fast-forward of the `release` branch.
