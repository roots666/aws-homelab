# aws-homelab
*Aws terraform and ansible home lab*

>  need to write a gitlab pipeline or github actions with which it will be possible to implement the infrastructure (terraform) and the system (ansible).
>  what is given:

- [ ] in clean AWS account, you need to create vpc, nacl, subnets (1 x public, 1 x private), sg, igw
- [ ] 2 ec2 instances - t2.small (those that are closed by free tier) (private subnets)
- [ ] 1 alb (public subnet): listener: port 80 (http), configure alb listener rules (https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-update-rules.html, https: / /registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/lb_listener_rule)
   check http header "Host" - if a request comes, for example, to test1.com, map traffic to the first instance. if on test2.com on the second
- [ ] on these instances, just add nginx + php-fpm (you can safely take roles from the ansible galaxy)
- [ ] take any RPM-based from AWS

> Nacl and SG -- State: Stateful or Stateless
Security groups are stateful: This means any changes applied to an incoming rule will be automatically applied to the outgoing rule. e.g. If you allow an incoming port 80, the outgoing port 80 will be automatically opened.
Network ACLs are stateless: This means any changes applied to an incoming rule will not be applied to the outgoing rule. e.g. If you allow an incoming port 80, you would also need to apply the rule for outgoing traffic.


