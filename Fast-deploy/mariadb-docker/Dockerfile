
FROM centos:7

ADD openstack.repo /etc/yum.repos.d/openstack.repo
ADD cinder.conf /etc/cinder/cinder.conf

RUN yum install -y hostname openstack-cinder

CMD cinder-manage db sync

mysql -u root --password=mynewpassword  <<EOF
GRANT ALL PRIVILEGES on cinder.* to 'cinder'@'localhost' identified by "cinder_123";
GRANT ALL PRIVILEGES on cinder.* to 'cinder'@'%' identified by "cinder_123";
EOF