# build

`kubash build`

### Environment Variables

First you should set an ssh key to be added to the
`authorized_keys` on the hosts, either set the key as an environment veriable directly as
```
export KEYS_TO_ADD='ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTY68No= adminuser@testbox'
```

Or alternatively give it an url to a set of pubkeys
```
export KEYS_URL='https://raw.githubusercontent.com/myorg/keys/master/keys'
```

### builder options

`--builder packer` This will build images using packer

`--builder coreos` This will download the official coreos images

### OS options

`--target-os ubuntu` This will build ubuntu images

`--target-os debian` This will build debian images

`--target-os fedora` This will build fedora images

`--target-os centos` This will build centos images

`--target-os coreos` This will build coreos images (* no packer build for this*)

#### Initializer specific options

`--target-os kubeadm` This will build centos images
with the addition of getting the kube repos added and kubeadm etc installed

`--target-os kubeadm2ha` This will build centos images
with the addition of prepping for the kubeadm2ha ansible playbook

`--target-os kubespray` This will build centos images
with the addition of prepping for the kubespray ansible playbook

`--target-os openshift` This will build centos images
with the addition of prepping for the openshift ansible playbook

### Target build

For the packer build you can specify alternate json files to use

`--target-build my-alternate.json` This must exist in `$KUBASH_DIR/pax/$target_os/my-alternate.json`

For the coreos option this sets the channel (stable,beta,alpha)

`--target-build beta`

### Asciinema example run

[![asciicast](https://asciinema.org/a/164070.png)](https://asciinema.org/a/164070)
