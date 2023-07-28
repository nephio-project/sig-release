# Releasing

1. [Create releases](https://github.com/nephio-project/test-infra/tree/main/assets)
   in repositories with image build jobs with the new release tag:
   - https://github.com/nephio-project/nephio
   - https://github.com/nephio-project/kpt-backstage-plugins
   - https://github.com/nephio-project/free5gc
1. Verify that the images have been successfully built and pushed with the new
   release tag:
   - [Prow](https://prow.nephio.io)
   - [Docker Hub](https://hub.docker.com/u/nephio)
1. Some images are not built by us yet. Tag these Docker images manually:
   - nephio/resource-backend-controller
   - nephio/network-config-operator
1. Update the images in the manifests to point to the new release tag:
   - https://github.com/nephio-project/nephio-packages
   - https://github.com/nephio-project/nephio-example-packages
   - https://github.com/nephio-project/free5gc-packages
1. Tag any updated packages with a new Porch version number. For example, if you
   changed the Kptfile in [pkg-example-amf-bp](https://github.com/nephio-project/free5gc-packages/tree/main/pkg-example-amf-bp)
   to use the new tag for the functions, and the current highest revision number
   for that package is `pkg-example-amf-bp/v3`, you need to tag the new one as
   `pkg-example-amf-bp/v4`. Note that the sandbox provisioning scripts no longer
   depend on the Porch revision numbers; instead they use the release tag.
   However, the user-facing versions in PackageVariant(Set) resources and `kpt`
   commands use the Porch revision numbers.
1. Create releases in the package repositories with the release tag.
   - https://github.com/nephio-project/nephio-packages
   - https://github.com/nephio-project/nephio-example-packages
   - https://github.com/nephio-project/free5gc-packages
1. Update the sandbox provisioning code:
   - Change the current release tag instances to the new one.
   - Update any e2e tests that use the Porch package version numbers to use the
     new ones.
1. Update the documentation to use the new release tag and the new Porch package
   version numbers.
1. Tag the documentation repository with the new release tag.
