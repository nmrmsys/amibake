amibake - AWS EC2 AMI Build & Deploy Tool
====

## Usage
 amibake [--profile &lt;prof&gt;] &lt;cmd&gt; [more params &amp; options]

    > amibake tag ami-xxxxxxxx amazonlinux:201703
    > amibake search amazonlinux:201703
    > 
    > # After writing AMIBakefile
    > amibake build
    > amibake push my_app:20170819
    > amibake run my_app:20170819

## AMIBakefile example

    > # AMIBakefile: my_app
    > MAINTAINER nmrmsys
    > FROM amazonlinux:201703
    > USER ec2-user
    > 
    > COPY html/index.html ~/
    > RUN sudo yum install -y httpd
    > RUN sudo chkconfig httpd on
    > RUN sudo mv ~/index.html /var/www/html/

## Requirement
- aws-cli version 1.6.x or later
- jq 
- packer 

## Licence

[MIT](http://opensource.org/licenses/mit-license.php)

## Author

[nmrmsys](https://github.com/nmrmsys)
