
trigger:
- main
pool:
  vmImage: 'ubuntu-latest'
steps:
- task: CmdLine@2
  displayName: Checkout $(Build.SourceBranchName)
  inputs:
    - script: 'git checkout $(Build.SourceBranchName)'
- script: curl -L 'https://get.spectralops.io/latest/x/sh?dsn=$(SPECTRAL_DSN)' | sh
  displayName: 'Install Spectral'
- script: $HOME/.spectral/spectral scan --ok --dsn $(SPECTRAL_DSN)
  displayName: 'Spectral Scan'
