# python example with google cloud functions

### requirements
`pip install -r requirements.txt`

### start cloud functions locally
`functions-framework --target hello_world --debug`

To execute the function open [http://localhost:8080/](http://localhost:8080/) in your browser and see Hello world! If you want to provide a parameter then use [http://localhost:8080/?message=HelloYou](http://localhost:8080/?message=HelloYou)

For all the details see [https://cloud.google.com/functions/docs/running/function-frameworks](https://cloud.google.com/functions/docs/running/function-frameworks)