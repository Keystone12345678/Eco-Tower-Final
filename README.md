name: Build Android App
on: 
  push:
    branches: [ main ]
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-22.04
    steps:
      - uses: actions/checkout@v4

      - name: Build with Buildozer
        uses: ArtemSerebrennikov/buildozer-action@v1
        with:
          command: buildozer android debug
          buildozer_version: master
