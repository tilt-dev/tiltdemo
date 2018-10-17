# -*- mode: Python -*-

def tiltdemo():
  yaml = read_file('deployment.yaml')
  image_name = 'gcr.io/windmill-test-containers/tiltdemo'
  start_fast_build('Dockerfile', image_name, '/go/bin/tiltdemo')
  repo = local_git_repo('.')
  add(repo, '/go/src/github.com/windmilleng/tiltdemo')
  run('go install github.com/windmilleng/tiltdemo')
  image = stop_build()
  return k8s_service(yaml, image)
