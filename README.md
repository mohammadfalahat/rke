# Rancher in a nutshell!

## Bastion server:

### Install Rancher Kubernetes Engine inside bastion server:

Watch for latest version here: https://github.com/rancher/rke/releases/tag

```

wget https://github.com/rancher/rke/releases/download/v1.4.10/rke_linux-arm64
chmod +x rke_linux-amd64
mv rke_linux-amd64 rke
sudo mv rke /usr/local/bin

```

### Collect and Publish Images to your Private Registry

Get bash scripts, Watch for latest version here: https://github.com/rancher/rancher/releases

```

wget https://github.com/rancher/rancher/releases/download/v2.7.6/rancher-load-images.sh
wget https://github.com/rancher/rancher/releases/download/v2.7.6/rancher-save-images.sh

```

See all kubernetes version supported list

```

# list all kubernetes version support
rke config --list-version

```

save list all image for all version in rancher-images.txt

```

# list all image for all version
rke config --list-version --all --system-images > rancher-images.txt

```

Run rancher-save-images.sh with the rancher-images.txt image list to create a tarball of all the required images:

```

chmod +x rancher-save-images.sh
./rancher-save-images.sh --image-list ./rancher-images.txt

```

