# eb-docker-sample

### EB CLI 명령 참조
https://docs.aws.amazon.com/ko_kr/elasticbeanstalk/latest/dg/eb3-cmd-commands.html

### init
```
eb init docker-sample \
--region ap-northeast-2 \
--platform docker \
--keyname aws-eb-sample-test
```
### develop env
```
eb create eb-docker-dev-env \
--region ap-northeast-2 \
--cname eb-docker-dev \
--platform docker-19.03.6-ce \
--instance_type t2.micro \
--single \
--tags Stage=test \
--sample
```

### production env
```
eb create eb-docker-prod-env \
--vpc.id vpc-0235ca8585ef56a29 \
--vpc.ec2subnets subnet-0f4b12559015b6dc9,subnet-065d1eb2bacdc8c76 \
--vpc.elbsubnets subnet-0defb6ab390d0a472,subnet-09365551f54288d7d \
--vpc.securitygroups sg-094c7b4e0e494ba06 \
--vpc.elbpublic \
--region ap-northeast-2 \
--cname eb-docker \
--platform docker-19.03.6-ce \
--instance_type t2.micro \
--scale 2 \
--elb-type application \
--tags Stage=prod
```
