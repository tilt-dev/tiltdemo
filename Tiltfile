# -*- mode: Python -*-

k8s_resource_assembly_version(2)

# tiltdemo1
k8s_yaml('demoserver1/k8s.yaml')
dm1_img_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver1'
docker_build(dm1_img_name, './demoserver1',
  live_update=[
    sync('./demoserver1/cmd', '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver1'),
    run('go install github.com/windmilleng/tiltdemo/cmd/demoserver1'),
    restart_container(),
  ]
)

# tiltdemo2
k8s_yaml('demoserver2/k8s.yaml')
dm1_img_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver2'
docker_build(dm1_img_name, './demoserver2',
  live_update=[
    sync('./demoserver2/cmd', '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver2'),
    run('go install github.com/windmilleng/tiltdemo/cmd/demoserver2'),
    restart_container(),
  ]
)

k8s_resource('demoserver1', port_forwards=8000)
k8s_resource('demoserver2', port_forwards=8001)
