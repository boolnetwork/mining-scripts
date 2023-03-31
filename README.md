# BOOLNetwork scripts

## Instructions

Before Getting Started, Check at [Intel© Ark](https://ark.intel.com/content/www/us/en/ark.html#@Processors) that your processor is [Intel© SGX](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html) compatible.

Clone the repo.

```bash
git clone https://github.com/boolnetwork/mining-scripts.git
```

## SGX

Check if SGX1 is Supported.
```
./sgx-detect
```

Output example:
```text
✔  SGX instruction set
  ✔  CPU support
  ✔  CPU configuration
  ✔  Enclave attributes
  ✔  Enclave Page Cache
  SGX features
    ✘  SGX2  ✘  EXINFO  ✘  ENCLV  ✘  OVERSUB  ✘  KSS  
    Total EPC size: 56.0MiB
✔  Flexible launch control
  ✔  CPU support
  ？ CPU configuration
  ✔  Able to launch production mode enclave
✔  SGX system software
  ✔  SGX kernel device (/dev/sgx/enclave)
  ✘  libsgx_enclave_common
  ✘  AESM service
  ✔  Able to launch enclaves
    ✔  Debug mode
    ✔  Production mode
    ✔  Production mode (Intel whitelisted)
```

## BOOLNetwork & Docker

Run with docker-compose

```bash
docker-compose up -d
```

More details about the config. [tee](https://boolnetwork.github.io/docs/developer/tee)


```
docker run -e RUST_LOG=info,tee=trace -itd -v `pwd`/node-data:/data -p 9934:9933 -p 9945:9944 --name bnk-node-test boolnetwork/bnk-node --dev --unsafe-ws-external --unsafe-rpc-external --rpc-cors all
```


