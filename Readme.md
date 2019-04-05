
[![GitHub license](https://img.shields.io/badge/license-ISC-blue.svg)](https://github.com/facebook/react/blob/master/LICENSE)  [![Build Status](https://travis-ci.org/Elyx0/touchtunes.svg?branch=master)](https://travis-ci.org/Elyx0/touchtunes/)[![Known Vulnerabilities](https://snyk.io/test/npm/snyk/badge.svg)](https://snyk.io/synk/github/elyx0/touchtunes) [![Coverage Status](https://coveralls.io/repos/github/Elyx0/touchtunes/badge.svg?branch=master)](https://coveralls.io/github/Elyx0/touchtunes?branch=master)


### Touchtunes test

The code is build with [Typescript](https://www.typescriptlang.org/)

#### Development

Locally:
`npm install && npm run build && npm local`

To get the code coverage:
`npm run coverage`

To run the tests in watch mode:
`npm run watch`

Precommits hooks using `husky` will run to check that the current work is acceptable for master:
- > Eslint / Tslint pass
- > 70% coverage with `nyc`

##### Debugging

`.vscode` launch options are provided for debugging locally

#### On Docker:

- Build the image: `npm run docker-build`
- Run the image: `npm run docker-run`

Head to `http://localhost:3000/health` you should see the response.

Check `docker images` & `docker ps`

Alternatively: `docker-compose up`

By default it will expose the app on the port `3000`:

Example call:

```bash
curl -X POST \
  http://localhost:3000/ \
  -H 'Cache-Control: no-cache' \
  -H 'Content-Type: application/json' \
  -d '{"settings":[{"name":"Mixer","requires":["audio","pcb"]},{"name":"AttractLoop","requires":[]},{"name":"Volume","requires":["audio"]},{"name":"Picture","requires":["camera"]},{"name":"Voice","requires":["microphone","audio"]},{"name":"Touch","requires":["pressure"]},{"name":"Weather","requires":["thermometer","clock"]},{"name":"Alarms","requires":["clock","audio"]}],"components":[{"name":"audio"},{"name":"LED array"},{"name":"clock"}]}'
```

Example response:
```json
[
    {
        "name": "Mixer"
    },
    {
        "name": "AttractLoop"
    },
    {
        "name": "Volume"
    },
    {
        "name": "Voice"
    },
    {
        "name": "Weather"
    },
    {
        "name": "Alarms"
    }
]
```


## Potential Improvements:

- Separate microservices for Settings / Components
- Load balancing using the /health endpoint
- Health endpoint should collect additional metrics when called
- AWS Lambda serverless to reduce costs + cold start warmup
- The express microservice should be its own NPM package acting as a base for all microservices
- Switching to a bloom filter if the number of components/settings gets insanely high (unlikely)
- Piping logs output to `pino`
- Caching of the Settings output hash in a fast memory db (Redis) and only recall if the hash changed
- Apache bench to stress test the app

---