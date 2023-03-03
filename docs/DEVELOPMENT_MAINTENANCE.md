# Modifications made to upstream chart
This is a high-level list of modifications that Big Bang has made to the upstream helm chart. You can use this as as cross-check to make sure that no modifications were lost during an upgrade process.

## chart/values.yaml
- Big Bang additions at the bottom of the values file
- Replace images with Iron Bank image
- add PullSecret.name = private-registry
- add an `enabled` value to the `tests` block  set to `false` by default

## chart/templates/tests/configmap.yaml
- add a conditional for `tests/enabled`

## chart/templates/tests/pod.yaml
- add a conditional for `tests/enabled`