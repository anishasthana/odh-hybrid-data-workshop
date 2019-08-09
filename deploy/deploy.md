# Deployment Instructions

This workshop  is deployed using the OpenDatahub Operator found [here](https://gitlab.com/opendatahub/opendatahub-operator).

## Instructions to deploy

1. Clone the opendatahub-operator repository.
2. Copy `my_environment_cr.yaml` to the root of the opendatahub-operator repository.
3. Follow the instructions for installation as found at [manual-installation](https://gitlab.com/opendatahub/opendatahub-operator/blob/master/docs/manual-installation.adoc).
4. Follow the instructions for Seldon and Kafka as found in [docs](https://gitlab.com/opendatahub/opendatahub-operator/tree/master/docs).
5. To Deploy Ceph, follow the instructions under `Ceph installation with the Rook operator` in the [reference architecture](https://opendatahub.io/arch.html)
