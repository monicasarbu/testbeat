# Testbeat

Welcome to Testbeat.

Ensure that this folder is at the following location:
`${GOPATH}/github.com/monicasarbu`

## Getting Started with Testbeat

### Requirements

* [Golang](https://golang.org/dl/) 1.6.2

### Init Project
To get running with Testbeat, run the following command:

```
make init
```

To commit the first version before you modify it, run:

```
make commit
```

It will create a clean git history for each major step. Note that you can always rewrite the history if you wish before pushing your changes.

To push Testbeat in the git repository, run the following commands:

```
git remote set-url origin https://github.com/monicasarbu/testbeat
git push origin master
```

For further development, check out the [beat developer guide](https://www.elastic.co/guide/en/beats/libbeat/current/new-beat.html).

### Build

To build the binary for Testbeat run the command below. This will generate a binary
in the same directory with the name testbeat.

```
make
```


### Run

To run Testbeat with debugging output enabled, run:

```
./testbeat -c testbeat.yml -e -d "*"
```


### Test

To test Testbeat, run the following command:

```
make testsuite
```

alternatively:
```
make unit-tests
make system-tests
make integration-tests
make coverage-report
```

The test coverage is reported in the folder `./build/coverage/`

### Update

Each beat has a template for the mapping in elasticsearch and a documentation for the fields
which is automatically generated based on `etc/fields.yml`.
To generate etc/testbeat.template.json and etc/testbeat.asciidoc

```
make update
```


### Cleanup

To clean  Testbeat source code, run the following commands:

```
make fmt
make simplify
```

To clean up the build directory and generated artifacts, run:

```
make clean
```


### Clone

To clone Testbeat from the git repository, run the following commands:

```
mkdir -p ${GOPATH}/github.com/monicasarbu
cd ${GOPATH}/github.com/monicasarbu
git clone https://github.com/monicasarbu/testbeat
```


For further development, check out the [beat developer guide](https://www.elastic.co/guide/en/beats/libbeat/current/new-beat.html).


## Packaging

The beat frameworks provides tools to crosscompile and package your beat for different platforms. This requires [docker](https://www.docker.com/) and vendoring as described above. To build packages of your beat, run the following command:

```
make package
```

This will fetch and create all images required for the build process. The hole process to finish can take several minutes.
