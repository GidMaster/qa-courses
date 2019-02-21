 docker run -d --name gitlab-runner-5 --restart always \
-v /srv/gitlab-runner/config:/etc/gitlab-runner \
-v /var/run/docker.sock:/var/run/docker.sock \
gitlab/gitlab-runner:latest 



docker exec -it gitlab-runner-5 gitlab-runner register \
  --non-interactive \
  --url "http://<Gitlab-URL>" \
  --registration-token "<TOKEN>" \
  --executor "docker" \
  --description "docker-in-docker" \
  --tag-list "docker,ubuntu,build,deploy,test,docker-in-docker" \
  --run-untagged \
  --locked="false" \
  --docker-image "docker:stable" \
  --docker-volumes /var/run/docker.sock:/var/run/docker.sock
  --docker-privileged