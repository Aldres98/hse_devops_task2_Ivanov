# hse_devops_task2_Ivanov

To solve this network problem, we should register our runner in the very same network, which we specified in our docker-compose


Use your gitlab IP (e.g. localhost:8080);
take registration token from /admin/runner while logged in as root usr;
network mode = runner bridge, as it's specified in a bridge network in docker-compose;

sudo docker exec -it devops-gitlab_runner_1 gitlab-runner register \
--non-interactive \
--url http://YOUR_GITLAB_IP \
--registration-token <YOUR_GITLAB_RUNNER_TOKEN> \
--executor docker \
--docker-image alpine:latest \
--docker-network-mode runner-bridge


devops-gitlab_runner_1 is docker image name, you can check it by docker ps
