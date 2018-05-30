# dataflow-example

https://cloud.google.com/dataflow/examples/wordcount-example

install maven and openjdk then
requires configuration of gcloud with correct service permissions

```
mvn compile exec:java \
  -Dexec.mainClass=com.example.WordCount\
  -Dexec.args="--project=<YOUR_PROJECT_ID> \
    --stagingLocation=gs://<YOUR_STAGING_DIRECTORY> \
    --runner=BlockingDataflowPipelineRunner \
    --output=gs://<YOUR_OUTPUT_PREFIX>"
```



