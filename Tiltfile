# -*- mode: Python -*-

repo = local_git_repo('.')

# tiltdemo1
k8s_yaml('deployments/demoserver1.yaml')
dm1_img_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver1'
fast_build(dm1_img_name, 'Dockerfile', '/go/bin/demoserver1') \
  .add(repo.path('cmd/demoserver1'),
      '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver1') \
  .run('go install github.com/windmilleng/tiltdemo/cmd/demoserver1')

# tiltdemo2
k8s_yaml('deployments/demoserver2.yaml')
dm2_img_name= 'gcr.io/windmill-test-containers/tiltdemo/demoserver2'
fast_build(dm2_img_name, 'Dockerfile', '/go/bin/demoserver2') \
  .add(repo.path('cmd/demoserver2'),
      '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver2') \
  .run('go install github.com/windmilleng/tiltdemo/cmd/demoserver2')
