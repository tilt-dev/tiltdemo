# -*- mode: Python -*-

k8s_resource_assembly_version(2)

# tiltdemo1
k8s_yaml('deployments/demoserver1.yaml')
dm1_img_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver1'
docker_build(dm1_img_name, '.', dockerfile='Dockerfile.server1',
  live_update=[
    sync('cmd/demoserver1', '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver1'),
    run('go install github.com/windmilleng/tiltdemo/cmd/demoserver1'),
    restart_container(),
  ]
)

# tiltdemo2
k8s_yaml('deployments/demoserver2.yaml')
dm1_img_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver2'
docker_build(dm1_img_name, '.', dockerfile='Dockerfile.server2',
  live_update=[
    sync('cmd/demoserver2', '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver2'),
    run('go install github.com/windmilleng/tiltdemo/cmd/demoserver2'),
    restart_container(),
  ]
)
