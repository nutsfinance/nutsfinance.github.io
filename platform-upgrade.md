# Future Upgrade

NUTS Platform is expected to evolve and upgrade in the future. It's flexible and extensible in design. Below are some upgrade scenarios.

## Upgrade of Existing Instrument Domain

Existing instrument domains are not upgradeable. They are expected to be stable once activated. If there is any vulnerability found in existing instruments, FSPs could deactivate the instrument to prevent newer issuances from being created.

## Upgrade of Escrows

The Escrows for new instrument domains can be upgraded. As both Instrument Escrow and Issuance Escrow are created by Escrow Factory while the Escrow Factory address is stored in Config, NUTS Platform could deploy a newer version of Escrow Factory and then update its address in Config.

Please note that this upgrade only affects new instrument domains created after the upgrade. For existing instrument domains, as they have persisted the Escrow Factory address locally, they are still using the old Escrow Factory to create new Issuance Escrows.

## Upgrade of Instrument Managers

The Instrument Manager for new instrument domains can be upgraded. Config maintains different versions of Instrument Manager Factories as a mapping. In activating new instruments, FSPs should specify the version of Instrument Manager to use.

When a new version of Instrument Manager is implemented, NUTS Platform admins could deploy its corresponding Instrument Manager Factory contract and updates its address in Config.

## Upgrade of Instrument Registry

Currently, Instrument Registry is not upgradeable. As Instrument Registry is very light-weight, it does not expect any upgrade in the near future. However, when an upgrade is required, NUTS Platform admins are likely to deploy the newer Instrument Registry and replace the existing one. Users can continue to use the existing Instrument Registry and its existing instrument domains are not affected. We expect to use ENS to reduce the user friction caused by the Instrument Registry upgrade in the future.

