# chromium-xvfb-js-java8
Javascript testing inside a Docker image with headless Google Chrome, node and Java8 (for Selenium). This container has been created for CI e2e testing purposes.

## Vue-CLI e2e testing
In this container you can run your vue-cli e2e testing.

```
$ docker run -v ~/your/vue-cli-proj:/usr/src/app \
-it tijnschmits/chromium-xvfb-js-java8 \
/usr/bin/npm run e2e
```

## Gitlab Continuous Integration
This container can be imported by your Gitlab Runner for integrating e2e to your CI setup.

A `.gitlab-ci.yml` example:

```
stages:
  - e2e

before_script:
    - npm install

e2e:
  stage: e2e
  image: tijnschmits/chromium-xvfb-js-java8
  script:
    - npm run e2e
```