---
license: |
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at
  
      https://www.apache.org/licenses/LICENSE-2.0
  
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
---

<!--begin-include-->
| Key | Default | Description | Since |
| --- | ------- | ----------- | ----- |
| celeborn.master.endpoints | `<localhost>:9097` | Endpoints of master nodes for celeborn client to connect, allowed pattern is: `<host1>:<port1>[,<host2>:<port2>]*`, e.g. `clb1:9097,clb2:9098,clb3:9099`. If the port is omitted, 9097 will be used. | 0.2.0 | 
| celeborn.metrics.capacity | `4096` | The maximum number of metrics which a source can use to generate output strings. | 0.2.0 | 
| celeborn.metrics.collectCritical.enabled | `false` | It controls whether to collect metrics which may affect performance. When enable, Celeborn collects them. | 0.2.0 | 
| celeborn.metrics.enabled | `true` | When true, enable metrics system. | 0.2.0 | 
| celeborn.metrics.sample.rate | `1.0` | It controls if Celeborn collect timer metrics for some operations. Its value should be in [0.0, 1.0]. | 0.2.0 | 
| celeborn.metrics.timer.sliding.window.size | `4096` | The sliding window size of timer metric. | 0.2.0 | 
| celeborn.shuffle.chuck.size | `8m` | Max chunk size of reducer's merged shuffle data. For example, if a reducer's shuffle data is 128M and the data will need 16 fetch chunk requests to fetch. |  | 
| celeborn.storage.hdfs.dir | `<undefined>` | HDFS dir configuration for Celeborn to access HDFS. |  | 
| celeborn.worker.commit.threads | `32` | Thread number of worker to commit shuffle data files asynchronously. |  | 
| celeborn.worker.deviceMonitor.check.interval | `60s` | Intervals between device monitor to check disk. |  | 
| celeborn.worker.deviceMonitor.checklist | `readwrite,diskusage` | Select what the device needs to detect, available items are: iohang, readwrite and diskusage. |  | 
| celeborn.worker.deviceMonitor.enabled | `true` | When true, worker will monitor device and report to master. |  | 
| celeborn.worker.deviceMonitor.sys.block.dir | `/sys/block` | The directory where linux file block information is stored. |  | 
| celeborn.worker.disk.reserve.size | `5G` | Celeborn worker reserved space for each disk. | 0.2.0 | 
| celeborn.worker.flusher.avgFlushTime.slidingWindow.size | `20` | The minimum flush count to enter a sliding window to calculate statistics about flushed time and count. | 0.2.0 | 
| celeborn.worker.flusher.buffer.size | `256k` | Size of buffer used by a single flusher. |  | 
| celeborn.worker.flusher.hdd.threads | `1` | Flusher's thread count used for write data to HDD disks. | 0.2.0 | 
| celeborn.worker.flusher.hdfs.threads | `4` | Flusher's thread count used for write data to HDFS. | 0.2.0 | 
| celeborn.worker.flusher.shutdown.timeout | `3s` | Timeout for a flusher to shutdown. | 0.2.0 | 
| celeborn.worker.flusher.ssd.threads | `8` | Flusher's thread count used for write data to SSD disks. | 0.2.0 | 
| celeborn.worker.graceful.shutdown.checkSlotsFinished.interval | `1s` | The wait interval of checking whether all released slots to be committed or destroyed during worker graceful shutdown | 0.2.0 | 
| celeborn.worker.graceful.shutdown.checkSlotsFinished.timeout | `480s` | The wait time of waiting for the released slots to be committed or destroyed during worker graceful shutdown. | 0.2.0 | 
| celeborn.worker.graceful.shutdown.enabled | `false` | When true, during worker shutdown, the worker will wait for all released slots to be committed or destroyed. | 0.2.0 | 
| celeborn.worker.graceful.shutdown.partitionSorter.shutdownTimeout | `120s` | The wait time of waiting for sorting partition files during worker graceful shutdown. | 0.2.0 | 
| celeborn.worker.graceful.shutdown.recoverPath | `<tmp>/recover` | The path to store levelDB. | 0.2.0 | 
| celeborn.worker.graceful.shutdown.timeout | `600s` | The worker's graceful shutdown timeout time. | 0.2.0 | 
| celeborn.worker.heartbeat.timeout | `120s` | Worker heartbeat timeout. |  | 
| celeborn.worker.metrics.prometheus.host | `0.0.0.0` | Worker's Prometheus host. | 0.2.0 | 
| celeborn.worker.metrics.prometheus.port | `9096` | Worker's Prometheus port. | 0.2.0 | 
| celeborn.worker.replicate.threads | `64` | Thread number of worker to replicate shuffle data. |  | 
| celeborn.worker.shuffle.commit.timeout | `120s` | Timeout for a Celeborn worker to commit a shuffle. | 0.2.0 | 
| celeborn.worker.storage.base.dir.number | `16` | How many directories will be create if 'base.dir' is not set. The directory name is a combination of 'dir.prefix' and from zero to "dir.number" step by one. No sub directory will be created. |  | 
| celeborn.worker.storage.base.dir.prefix | `/mnt/disk` | Base directory for Celeborn worker to write if 'base.dir' is not set. |  | 
| celeborn.worker.storage.dirs | `<undefined>` | Directory list to store shuffle data. It's recommended to configure one directory on each disk. Storage size limit can be set for each directory. For the sake of performance, there should be no more than 2 flush threads on the same disk partition if you are using HDD, and should be 8 or more flush threads on the same disk partition if you are using SSD. For example: dir1[:capacity=][:disktype=][:flushthread=],dir2[:capacity=][:disktype=][:flushthread=] |  | 
| celeborn.worker.writer.close.timeout | `120s` | Timeout for a file writer to close | 0.2.0 | 
| celeborn.worker.writer.create.maxAttempts | `3` | Retry count for a file writer to create if its creation was failed. |  | 
<!--end-include-->