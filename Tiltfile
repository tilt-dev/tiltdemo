# -*- mode: Python -*-

def tiltdemo1():
  yaml = read_file('deployments/demoserver1.yaml')
  image_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver1'
  start_fast_build('Dockerfile', image_name, '/go/bin/demoserver1')
  repo = local_git_repo('.')
  add(repo.path('cmd/demoserver1'),
      '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver1')
  run('go install github.com/windmilleng/tiltdemo/cmd/demoserver1')
  image = stop_build()
  return k8s_service(yaml, image)

def tiltdemo2():
  yaml = read_file('deployments/demoserver2.yaml')
  image_name = 'gcr.io/windmill-test-containers/tiltdemo/demoserver2'
  start_fast_build('Dockerfile', image_name, '/go/bin/demoserver2')
  repo = local_git_repo('.')
  add(repo.path('cmd/demoserver2'),
      '/go/src/github.com/windmilleng/tiltdemo/cmd/demoserver2')
  run('go install github.com/windmilleng/tiltdemo/cmd/demoserver2')
  image = stop_build()
  return k8s_service(yaml, image)

def tiltdemo():
  return composite_service([tiltdemo1, tiltdemo2])
