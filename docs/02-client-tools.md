# Installing the Client Tools

In this lab you will install the command line utilities required to complete this tutorial: [cfssl](https://github.com/cloudflare/cfssl), [cfssljson](https://github.com/cloudflare/cfssl), and [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl).


## Install CFSSL

The `cfssl` and `cfssljson` command line utilities will be used to provision a [PKI Infrastructure](https://en.wikipedia.org/wiki/Public_key_infrastructure) and generate TLS certificates.

Download and install `cfssl` and `cfssljson`:

### OS X

```
curl -o cfssl https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssl_1.6.4_linux_amd64
curl -o cfssljson https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssljson_1.6.4_linux_amd64
```

```
chmod +x cfssl cfssljson
```

```
sudo mv cfssl cfssljson /usr/local/bin/
```

Some OS X users may experience problems using the pre-built binaries in which case [Homebrew](https://brew.sh) might be a better option:

```
brew install cfssl
```

### Linux

```
wget -q --show-progress --https-only --timestamping \
   https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssl_1.6.4_linux_amd64 \
   https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssljson_1.6.4_linux_amd64
```

```
chmod +x cfssl_1.6.4_linux_amd64 cfssljson_1.6.4_linux_amd64
```

```
sudo mv cfssl_1.6.4_linux_amd64 /usr/local/bin/cfssl
sudo mv cfssljson_1.6.4_linux_amd64 /usr/local/bin/cfssljson
```

Or

```
curl -s -L -o cfssl https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssl_1.6.4_linux_amd64
curl -s -L -o cfssljson https://github.com/cloudflare/cfssl/releases/download/v1.6.4/cfssljson_1.6.4_linux_amd64
```

### Verification

Verify `cfssl` and `cfssljson` version 1.6.4 or higher is installed:

```
cfssl version
```

> output

```
Version: 1.6.4
Runtime: go1.18
```

```
cfssljson --version
```
```
Version: 1.6.4
Runtime: go1.18
```

## Install OpenSSL

```
openssl version
```

```
OpenSSL 3.0.10 1 Aug 2023 (Library: OpenSSL 3.0.10 1 Aug 2023)
```

## Install kubectl

The `kubectl` command line utility is used to interact with the Kubernetes API Server. Download and install `kubectl` from the official release binaries:

### OS X

```
curl -o kubectl https://storage.googleapis.com/kubernetes-release/release/v1.29.1/bin/darwin/amd64/kubectl
```

```
chmod +x kubectl
```

```
sudo mv kubectl /usr/local/bin/
```

### Linux

```
gsutil cp gs://kubernetes-release/release/v1.29.1/bin/linux/amd64/kubectl ./
```

```
chmod +x kubectl
```

```
sudo mv kubectl /usr/local/bin/
```

### Verification

Verify `kubectl` version 1.29.1 or higher is installed:

```
kubectl version --client
```

> output

```
Client Version: v1.29.1
Kustomize Version: v5.0.4-0.20230601165947-6ce0bf390ce3
```

Next: [Provisioning Compute Resources](03-compute-resources.md)
