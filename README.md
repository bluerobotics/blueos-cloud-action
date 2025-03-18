# BlueOS Cloud Action

## Usage

A basic example of this action can be seen bellow:


```yaml
name: Build and publish your extension

on:
  workflow_dispatch:
  push:
    tags:
      - '*.*.*'
      - 'v*.*.*'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Build and Publish Extension in BlueOS CLoud
        uses: bluerobotics/blueos-cloud-action@0.0.3
        with:
          BCLOUD_PAT: ${{secrets.BCLOUD_PAT}}
          PLATFORMS: linux/arm/v7,linux/arm64,linux/amd64
          EXTENSION: <PUT-YOUR-EXTENSION-ID-HERE>
```

### What is a PAT and where I can get one?

Personal access tokens are an alternative to using passwords for authentication to BlueOS Cloud when using the cloud API
or the command line.

You can create one by going into [BlueOS cloud settings > Programmatic access](https://app.blueos.cloud/account/user/token/) 

### Where can I find my extension id?

After you create your extension in BlueOS Cloud Studio, you will see field called **Container image**, this string is composed by the registry url, plus your extension id:

    <registry-url>/<extension-id>

![image](https://github.com/user-attachments/assets/695348a6-5f0f-470d-825c-29c09f65c56c)
