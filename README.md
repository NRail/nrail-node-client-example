# NRail-Node-Client-Example
This is an example implementation to the RapidAPI NRail vehicle API.

This API can be used to pull periodic data from the NRail IoT platform and push it to your system.
In this example implements only the `/live-data/all` endpoint.

## Installation and Usage

1. Copy the values from [./.env.example](./.env.example) file to **.env** and add keys.
2. Goto [RapidAPI](https://rapidapi.com/nrail/api/nrail-vehicle-api) to subscribe to the API and get your **RAPID_API_KEY** (called `X-RapidAPI-Key` at RapidAPI). The API key can be found in the example request of the [route](https://rapidapi.com/nrail/api/nrail-vehicle-api/playground/apiendpoint_44b33c82-957d-4ce7-aaff-8cd26828efe7).
3. Goto [NRail IoT platform](https://iot.nrail.de) to get your **NRAIL_TOKEN**.
After logging in to iot.nrail.de with the technical user, you can create a new token on [this page](https://iot.nrail.de/settings/preferences).
You can also test your query on [this page](https://rapidapi.com/nrail/api/nrail-vehicle-api/playground/).
4. Start the service locally
```
npm i --package-lock
npm start
```
#### Alternative using docker
4. Run it via ephermeral docker container.
```
docker run \
    -ti \
    --rm \
    -p 5000:5000 \
    -v $PWD:/app node:22-alpine \
        /bin/sh -c "cd /app; npm i --package-lock; npm start"
```

5. Now you can access the Status page [http://localhost:5000](http://localhost:5000)

## API specs
Check the [./nrail-vehicle-api.html](./nrail-vehicle-api.html) file for documentation.


### Disclaimer
The project is for demonstration purposes and distributed as is. 
It is not intended for production usage and should serve only as a starting point.

The Node dependency in the package.json is required to ensure the project is run on Node >= v21.0.0.