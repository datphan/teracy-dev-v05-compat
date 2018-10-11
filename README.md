# teracy-dev-v05-compat

The extension to use to help to port teracy-dev from v0.5's features to teracy-dev v0.6

So when this extension is used for teracy-dev v0.6, `teracy-dev` will have all the supported features
from v0.5


## How to use

Configure `workspace/teracy-dev-entry/config_default.yaml` with the following similar content:

```yaml
teracy-dev:
  extensions:
    - _id: "entry-0"
      path:
        extension: teracy-dev-v05-compat
      location:
        git: https://github.com/teracyhq-incubator/teracy-dev-v05-compat.git
        branch: develop
      require_version: ">= 0.1.0-SNAPSHOT"
      enabled: true
```


## How to develop

You should configure the forked git repo into the `workspace` directory by adding the following
similar content into `workspace/teracy-dev-entry/config_override.yaml`:


```yaml
teracy-dev:
  extensions:
    - _id: "entry-0" # must match the _id configured from the config_default.yaml file
      path:
        lookup: workspace # use workspace directory to lookup for this extension
      location:
        git: git@github.com:hoatle/teracy-dev-v05-compat.git # your forked repo
        branch: develop
      require_version: ">= 0.1.0-SNAPSHOT"
```
