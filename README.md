# tiltdemo

Demo servers for running the tilt demo script.

## Usage

To see the demo:

```
go get -u github.com/windmilleng/tilt
tilt demo
```

`tilt` will check out this repository and run these servers interactively
on your favorite Kubernetes cluster.

To run the servers locally:

```
tilt up tiltdemo
```

## License

Copyright 2018 Windmill Engineering

Licensed under [the Apache License, Version 2.0](LICENSE)