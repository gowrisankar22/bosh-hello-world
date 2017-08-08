# Upload cloud config
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
