# Nephio SIG-Release R1 Work Areas

## R1
For R1, SIG-Release can be divided into the following two areas:
1. Release management (branch strategy, release process, dates, and guidelines)
1. Test infra and tools (testbed, unit test framework, integration test framework)

### Release Management
For R1, SIG-Release aims to appoint two release managers to oversee the entire release process. The tasks include:
- release process definition
- branch strategy, release tags
- ensure release quality via ensuring release functionality and test coverage
- PROW tasks: CLA plugin, branch labels
- release criteria definition

**Primary Skills**
- release management
- program / project management
- git
- PROW

### Test Infra and Tools
This area includes:
- enhancing the current test setup from ONE Summit to:
  - allow for different network topology
  - VLAN to subnet mapping
  - flexible set up of additional KIND cluster (i.e., "cloud" cluster for AMF)
  - packet sniffing
- unit test framework
- integration test framework

**Primary Skills**
- ansible
- terraform
- KIND clusters
- scripting language
- Golang
