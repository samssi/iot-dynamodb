# iot-dynamodb

## Database design

### Table

Table corresponds as single sensor. Sensor/table naming convetion is <sensor_type>_<uuid>. Type and uuid for sensor can be found from the sensory device itself from <ADD_LOCATION_HERE_WHEN_AVAILABLE>

### Item

Item key corresponds to measurement time. A single sensor (which is reprerented by the table) can not have duplicate measurement times and therefore it can be used as the primary key.

#### Attribute

Attributes use epoch time to represent time. Time unit is always the type Number 'N'.

## Running DynamoDB locally

### Dockerized DynamoDB

```
docker run -d -p 8000:8000 dwmkerr/dynamodb
```

### DynamoDB Client Query examples for local development

```
aws dynamodb create-table --cli-input-json file:///dir/to/tabledefinition.json --endpoint-url http://localhost:8000
```

```
aws dynamodb create-table --cli-input-json file:///dir/to/tabledefinition.json --endpoint-url http://localhost:8000
```

```
aws dynamodb put-item --cli-input-json file:///dir/to/tabledefinition.json --endpoint-url http://localhost:8000
```