# btrtl-8671bfix
Bluetooth driver kernel module fixing Realtek RTL8761B chip misidentification per [this gist](https://gist.github.com/rometsch/dfd24fb09c85c1ad2f25223dc1481aaa).

# Build and install with DKMS

DKMS is a tool for automatically rebuilding and installing kernel modules to new kernels when they are installed. You can install it and the necessary dependencies via:

```
sudo apt-get install dkms linux-headers-$(uname -r) build-essential
```

Then, you can install this specific module via:

```
sudo mkdir /usr/src/btrtl-0.1fixed
git archive master | sudo tar -x -C /usr/src/btrtl-0.1fixed
sudo dkms install -m btrtl -v 0.1fixed --force
```
