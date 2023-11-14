# python example with google cloud functions

### requirements
`pip install -r requirements.txt`

### start cloud functions locally
`functions-framework --target hello_world --debug`

To execute the function open [http://localhost:8080/](http://localhost:8080/) in your browser and see Hello world! If you want to provide a parameter then use [http://localhost:8080/?message=HelloYou](http://localhost:8080/?message=HelloYou)

For all the details see [https://cloud.google.com/functions/docs/running/function-frameworks](https://cloud.google.com/functions/docs/running/function-frameworks)

### deployment with gcloud console

`gcloud init`

```
gcloud functions deploy python-http-function \
    --gen2 \
    --runtime=python312 \
    --region=europe-west4 \
    --source=. \
    --entry-point=hello_get \
    --trigger-http
```

gcloud functions deploy python-http-function --gen2 --runtime=python312 --region=europe-west4 --source=. --entry-point=hello_world --trigger-http

Al termine del deployment della funzione, prendi nota della proprietà uri o cercala utilizzando il seguente comando:
`gcloud functions describe python-http-function --gen2 --region europe-west4 --format="value(serviceConfig.uri)"`

call
```
curl -m 70 -X POST URI \
    -H "Authorization: Bearer $(gcloud auth print-identity-token)" \
    -H "Content-Type: application/json" \
    -d '{}'
```

curl -m 70 -X POST http://europe-west4-experiments-375419.cloudfunctions.net/python-http-function  -H "Authorization: Bearer $(gcloud auth print-identity-token)" -H "Content-Type: application/json" -d '{}'