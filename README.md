
A composite workflow to load a cyber-dojo image from a docker registry.


Typical use is as follows:

```yml
name: Main

...

jobs:
  snyk-container-scan:
    runs-on: ubuntu-latest
    steps:
      ...


...
```
