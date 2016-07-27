#Amazon EB deployment for Wercker.com


[![wercker status](https://app.wercker.com/status/ff5cec33194ea3c318288128f970c134/m "wercker status")](https://app.wercker.com/project/bykey/ff5cec33194ea3c318288128f970c134)

> Please note: This requires you to have an already existing Elastic Beanstalk application and environment in place, it will not run a startup procedure.

* `key` (required) Credentials key provided by amazon.
* `secret` (required) Credentials key secret provided by amazon
* `app_name` (required) Name of the application.
* `env_name` (required) Name of the application environment you wish to deploy to.
* `artifact` (required) Path to the artifact that will be deployed to your elastic beanstalk application.
* `region` (optional) Region that your elastic beanstalk instance lives in, defaults to us-west-2.
* `platform` (optional) The platform that the artifact will be deployed on. Currently defaults to: 64bit Amazon Linux 2016.03 v2.1.3 running Docker 1.11.1
* `nohup` (optional) Deploying background jobs.
* `opts` (optional) eb deploy options. ex) `--staged`

```yml
deploy:
    steps:
        - hotakasaito/elastic-beanstalk-deploy:
            key: $AMAZON_KEY
            secret: $AMAZON_SECRET_KEY
            app_name: My Application
            env_name: production
            region: us-west-2
            platform: 64bit Amazon Linux 2016.03 v2.1.3 running Docker 1.11.1
            artifact: $WERCKER_OUTPUT_DIR/deploy/docker.zip
            nohup: true
            opts: --staged
```
