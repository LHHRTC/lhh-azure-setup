# LHH Azure setup

One time setup template for the private LHH Governance app. It holds no secrets and no data.

It creates, in the owner's Azure subscription:
- resource group `rg-lhh-governance`
- deploy identity `id-lhh-governance-deploy`: Contributor on that resource group only, usable only by GitHub Actions in `LHHRTC/lhh-governance`
- operator identity `id-lhh-governance-operator`: Reader and Monitoring Reader on that resource group only
- budget `lhh-monthly`: $60 a month, emails the subscription owners at 80% and on forecast overrun

The source of truth is `infra/bootstrap.json` in the private repository; this copy exists because Azure's Deploy to Azure link needs a public address.
