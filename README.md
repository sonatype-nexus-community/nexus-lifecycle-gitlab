## nexus-lifecycle-gitlab

This docker image is designed to be used as a Gitlab Runner for performing [Sonatype Lifecycle](https://www.sonatype.com/nexus-lifecycle "Would you like to know more?") scans

## Example runner

```yaml
evaluate-build:
    stage: test
    image: registry.gitlab.com/sonatype-nexus-community/nexus-lifecycle-gitlab:latest
    variables:
        IQ_URL: http://lifecycle.mycompany.com:8070
        IQ_AUTH: admin:admin123
        IQ_STAGE: build
        IQ_APPID: awesomeApp
    script:
        - evaluate
    after_script:
        - gitlab
    only:
        - master
```

## The Fine Print
It is worth noting that this is **NOT SUPPORTED** by Sonatype, and is a contribution of HokieGeek
plus us to the open source community (read: you!)

Remember:

* Use this contribution at the risk tolerance that you have
* Do **NOT** file Sonatype support tickets related to this
* **DO** file issues here on GitHub, so that the community can pitch in
