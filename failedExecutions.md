### Failed Executions
(Didn't add toolkit api and Internal Server errors)

Occured on June 26
```
execution: https://us-east-1.console.aws.amazon.com/states/home?region=us-east-1#/v2/executions/details/arn:aws:states:us-east-1:346945241475:execution:0xtgrlvtqlSTATEMACHINE:0dcd825a-e7a6-4be5-be8f-44f562bd4e78

Reason: One of the extracted edges contained       
      {
        "source": "What",
        "type": null,
        "target": null
      },
      The null target caued the error

This can be handled by adding a check that source and target should not be in ["", " ", "None", null]
```

Occured on June 23
```
Execution: https://us-east-1.console.aws.amazon.com/states/home?region=us-east-1#/v2/executions/details/arn:aws:states:us-east-1:346945241475:execution:0xtgrlvtqlSTATEMACHINE:7ccb1bbf-1677-4fe9-bf13-9bc74e663526

{
  "errorMessage": "local variable 'relation_type_disambiguation_dict' referenced before assignment",
  "errorType": "UnboundLocalError",
  "stackTrace": [
    "  File \"/var/task/chalice/app.py\", line 1753, in __call__\n    return self.handler(event_obj)\n",
    "  File \"/var/task/chalice/app.py\", line 1699, in __call__\n    return self._original_func(event.to_dict(), event.context)\n",
    "  File \"/var/task/chalicelib/services/query_pipeline.py\", line 597, in disambiguate_relationships_on_kg\n    \"relation_type_disambiguation_dict\": relation_type_disambiguation_dict,\n"
  ]
}
```


Occured on June 21
```
Execution: https://us-east-1.console.aws.amazon.com/states/home?region=us-east-1#/v2/executions/details/arn:aws:states:us-east-1:346945241475:execution:0xtgrlvtqlSTATEMACHINE:ee25a70d-1cc5-43a0-b9ff-f94dd6b61124

{
  "errorMessage": "An error occurred (GoneException) when calling the PostToConnection operation: ",
  "errorType": "GoneException",
  "stackTrace": [
    "  File \"/var/task/chalice/app.py\", line 1753, in __call__\n    return self.handler(event_obj)\n",
    "  File \"/var/task/chalice/app.py\", line 1699, in __call__\n    return self._original_func(event.to_dict(), event.context)\n",
    "  File \"/var/task/chalicelib/services/query_pipeline.py\", line 914, in generate_answer\n    post_to_connection(\n",
    "  File \"/var/task/chalicelib/utils/query_pipeline_utils.py\", line 40, in post_to_connection\n    apig_management.post_to_connection(\n",
    "  File \"/var/task/botocore/client.py\", line 530, in _api_call\n    return self._make_api_call(operation_name, kwargs)\n",
    "  File \"/var/task/botocore/client.py\", line 960, in _make_api_call\n    raise error_class(parsed_response, operation_name)\n"
  ]
}

This has occuered twice in the past week.
I have found that the GoneException can occur when the client that initiated the websocket has disconnected from the socket and its connectionId can no longer be found.
I was not able to find the exact reason.
```