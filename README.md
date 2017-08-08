# Upload cloud config
This cloud config is for Google Cloud Platform (europe-west-1-b) based on the cloud config found in: https://github.com/FINkit/learn-bosh-on-gcp-release
```
cd ~/
git clone https://github.com/dazjones/bosh-cloud-configs
bosh ucc bosh-cloud-configs/gcp/cloud-config-europe-west-1.yml
```

# Upload stemcell
```
cd ~/
wget https://s3.amazonaws.com/bosh-core-stemcells/google/bosh-stemcell-3431.13-google-kvm-ubuntu-trusty-go_agent.tgz
bosh upload-stemcell bosh-stemcell-3431.13-google-kvm-ubuntu-trusty-go_agent.tgz
```

# Create, upload and deploy release
```
cd ~/
git clone https://github.com/dazjones/bosh-hello-world
cd bosh-hello-world
bosh create-release
bosh upload-release
bosh -d bosh-hello-world deploy manifest.yml
```
