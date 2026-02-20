
A composite workflow to load a cyber-dojo image from a docker registry.


Typical use is as follows:

```yml
name: Main

...

jobs:
  snyk-container-scan:
    needs: [build-image]
    runs-on: ubuntu-latest
    permissions:
      id-token: write
      contents: write
    env:
      IMAGE_NAME: ${{ needs.build-image.outputs.tagged_image_name }}
    steps:
      ...
      - name: Load image from registry
        uses: cyber-dojo/load-image-from-registry@main

      - name: Do something with image
        run:
          ... "${IMAGE_NAME}" ...

...
```
