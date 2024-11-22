# opsrule

## Schema OpsRule

OpsRule describes operation rules for various Day-2 Operations. Once declared, these<br />operation rules will be checked before any Day-2 operations.

### Attributes

| name | type | description | default value |
| --- | --- | --- | --- |
|**maxUnavailable**|int | str|The maximum percentage of the total pod instances in the component that can be<br />simultaneously unhealthy.|"25%"|

```python
import opsrule as o
import kam.v1.app_configuration
import kam.v1.workload as wl
import kam.v1.workload.container as c

helloworld : ac.AppConfiguration {
    workload: service.Service {
        containers: {
            "nginx": c.Container {
                image: "nginx:v1"
            }
        }
    }
    accessories: {
        "opsrule" : o.OpsRule {
            maxUnavailable: "30%"
        }
    }
}
```

<!-- Auto generated by kcl-doc tool, please do not edit. -->