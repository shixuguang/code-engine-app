### deploy code-engine-app to byoa

```
    cpd-cli manage create-gitapp-application --cpd_instance_ns=zen 
        --app_name=code-engine  
        --app_port=3000
        --app_port_tls=false
        --repo_url=https://github.ibm.com/Code-Engine/code-engine-handson-sample-app.git
        --token=<github.ibm.com token>
        --app_envs='[{"name":"BUCKETNAME","value":"test-bucket-viabwuakuy68lh6"},{"name":"TESTVALUE","value":"mytest"},{"name":"COS_ENDPOINT","value":"s3.us-south.cloud-object-storage.appdomain.cloud"},{"name":"COS_APIKEY","value":"<my api key>"},{"name":"COS_RESOURCE_INSTANCE_ID","value":"ca2dd396-de85-4ab1-9762-9a4f3788133a"},{"name":"HOME", "value":"/tmp"}]'  
        --app_proxy_config_yaml='https://raw.githubusercontent.com/shixuguang/code-engine-app/refs/heads/main/code-engine-app.conf.yaml'  
        --cpu=400m
        --memory=200Mi
        --cpu_limit=500m
        --memory_limit=400Mi

        app_run_id will be returned from deployment
```

#### application available at `https://zen-route/physical_location/ocp4813-default/<app_name>-<app_run_id>/`