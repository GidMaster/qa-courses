builld: setVariable gitlab-ci

setVariable:
	echo external_url=http://$(docker-machine ip qa-gitlab-ci) > .env

gitlab-ci:
	docker-compose up -d
