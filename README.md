

## Usage

```yaml
name: Build and publish your extension

on:
  workflow_dispatch:
  push:
    tags:
      - '*.*.*'

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Build and Publish Extension in BlueOS CLoud
        uses: bluerobotics/blueos-cloud-action@0.0.1
        with:
          BCLOUD_PAT: ${{secrets.BCLOUD_PAT}}
          PLATFORMS: linux/arm/v7,linux/arm64,linux/amd64
          EXTENSION: <PUT-YOUR-EXTENSION-ID-HERE>
```