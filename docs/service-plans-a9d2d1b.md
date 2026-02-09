<!-- loioa9d2d1b5306d4da08ed0d0e38b2850f0 -->

# Service Plans

The SAP Cloud Logging service plans provide different ingestion and storage capabilities.

> ### Note:  
> Updating service plans isn't supported. The recommended migration procedure involves running instances side-by-side during a transition.

> ### Note:  
> Service plans impact pricing. Pricing information is available via [Discovery Center](https://discovery-center.cloud.sap/serviceCatalog/cloud-logging?tab=service_plan) and [SAP Cloud Logging Capacity Unit Estimator](https://sap-cloud-logging-estimator.cfapps.us10.hana.ondemand.com/).

> ### Caution:  
> For production service plans, service instances scale automatically within the configured limits. To avoid disk overflow, there is time-based and disk-utilization-based data curation. If the disk usage watermark has been exceeded and the instance is scaled to its maximum, the system automatically deletes the oldest indices. The term `net storage capacity` used in service plan descriptions refers to the usable disk-size up to the watermark and has subtracted the disk space required for replicas. Service plans can handle peak load in relation to their storage volumes. However, service quality degradation can happen if the load exceeds the non-scaled disk capacity within one day.

To get an overview on the availability of SAP Cloud Logging according to region, infrastructure provider, and release status, visit the [SAP Discovery Center](https://discovery-center.cloud.sap/protected/index.html#/serviceCatalog/cloud-logging).



<a name="loioa9d2d1b5306d4da08ed0d0e38b2850f0__section_ddx_db5_zyb"/>

## Development Plan

The `dev` plan is only for evaluation purposes. It must not be used in production use cases, as it lacks cloud qualities. It also doesn't include auto-scaling or data replication, and has limited ingestion throughput. Therefore it isn't suitable for testing loads exceeding its 7.5 GiB storage capacity.



<a name="loioa9d2d1b5306d4da08ed0d0e38b2850f0__section_b2x_fb5_zyb"/>

## Standard Plan

The `standard` plan targets usage in production. It incorporates data replication, and enables automatic scaling of net storage capacity from 75 GiB to 375 GiB.

> ### Example:  
> If the average ingest rate is 100 x 2 KiB logs per second, a single standard plan instance can sustain storage for approximately 7 to 34 days, depending on the specific scaling configuration and including indexing and compression factors.



<a name="loioa9d2d1b5306d4da08ed0d0e38b2850f0__section_ak4_2c5_zyb"/>

## Large Plan

The `large` plan targets usage in production. It incorporates data replication and enables automatic scaling of net storage capacity from 750 GiB to 3.75 TiB.

> ### Example:  
> If the average ingest rate is 1000 x 2 KiB logs per second, a single large plan instance can sustain storage for approximately 7 to 34 days, depending on the specific scaling configuration and including indexing and compression factors.

