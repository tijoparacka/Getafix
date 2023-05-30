# Getafix
We introduce our state-of-the-art tool viz Getafix, that has been specifically designed for the effective tuning of Apache Druid clusters, focusing on three key factors: configuration parameters, query tuning, and data modeling based on usage patterns. However, Getafix puts particular emphasis on the first and third factors to provide a specialized, more targeted approach.

In the realm of configuration parameters, our tool ensures to optimize your Druid cluster to the best possible extent. These parameters include but are not limited to memory settings, thread pools, and query capacities. You can effortlessly adjust these parameters to the specific requirements of your Druid cluster, ensuring optimum performance and utilization.

While our tool doesn't directly deal with query tuning, the second factor, it's important to note that well-configured parameters can indirectly contribute to more efficient query execution, thus enhancing overall system performance.

The third factor, data modeling based on usage patterns, is another area where our tool excels. With the aid of Getafix, it comprehends your cluster's data dynamics and adaptively remodels the data based on changing usage patterns. This ensures your Druid cluster remains efficient and delivers top-notch performance, even with shifting data demands and usage trends.

By combining these functionalities, the tool delivers a streamlined approach to Apache Druid cluster tuning. It simplifies the intricate process of cluster optimization and provides valuable insights into data usage patterns, leading to an exceptionally well-tuned and high-performing Apache Druid environment.

##Approach##
Its recommend to do a cluster health check on a regular interval to ensure that the cluster is always tuned even with the changing the query patterns. 

A cluster review scorecard used to evaluate the configuration and operation of Apache Druid clusters.

Designed to be executed in a cumulative way, depending on your interest and ability to collect information.

## Analysis types planned

1. Run API queries against the cluster to get information about datasources, compaction etc. *
2. Add node size info and and compare to Druid cluster guidelines for this
3. Collect Broker logs to understand best practices for partitioning, tiering
4. Collect metrics (Clarity / Logs / Prometheus) information to identify hotspots / trends

## Data collection methods

### Druid API collector

**Currently collected**

| API query | Description |
| --- | --- |
| compaction | Configuration of compaction for each applicable datasource |
| compaction status | Current status of compaction for each applicable datasource |
| coordinator dynamic config | Current configuration of the coordinator dynamic configuration |
| datasources | Detailed information for all segments contained in each datasource |
| lookups | Configuration information for all configured lookups |
| overlord dynamic config | Current configuration of the overlord dynamic configuration |
| retention | Current retention policies for all configured datasources |
| segments | Number of segments, average size and average number of rows for each datasource |
| servers | List of servers (services) which comprise the cluster |
| supervisors | Details of configured supervisors |
| tasks | A snapshot of recently run tasks |
| workers | Number of workers available |

******To add******

`/status/properties` from all available services to understand Druid tuning parameters

### Log upload

### Metrics collection

## Rule based evaluation

Evaluate data based on [cDMN](https://cdmn.readthedocs.io/en/latest/notation.html) - can be expressed in XLS or DMN file types

file:///Users/khoondert/Documents/Data/Dev/temp/Getafix.html