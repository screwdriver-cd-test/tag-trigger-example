# Tag Trigger Example

To execute a job by a tag push event in Screwdriver.cd, you can specify `~tag` requires property about your arbitrary jobs.

### Example

```
jobs:
    test-job:
        image: node:10
        steps:
            - echo: echo 'this is test job.'
        requires: [~commit, ~pr]
    tag-triggered-job:
        image: node:10
        steps:
            - echo: |
                echo 'this job is executed by a tag push event.'
        requires: [~tag]
```

In the above example, the `tag-triggered-job` is started when you push a tag (e.g. `v0.1.0`).
