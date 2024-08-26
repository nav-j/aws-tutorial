# How to run a static HTML+CSS website on AWS Freetier EC2 instance.

1. Make sure you have free EC2 instance if not follow this [link](https://github.com/nav-j/aws-tutorial/blob/main/launch-ec2.md)
2. Ensure you have `httpd` and `git` packages installed
```bash
yum install httpd git -y
```
3. Clone the git repository,if it is `private` repository follow the following command :
```bash
git clone https://user:token@github.com/repo-url.git
```     
4. Copy Website files to `/var/www/html` and set required permissions.
```bash
cp -r wise-website/cyber-sec-project/* /var/www/html/
chown -R root.apache /var/www/html
restorecon -rvf /var/www/html
```
5. Start and enable **httpd** service
```bash
systemcl enable httpd --now
```
6. Now try to access the website with curl
```bash
curl localhost
```
7. If website is accessible with `curl` then try to access it in a web browser with **Public IP** of your EC2 instance. In order to find the public IP navigate to `AWS Console > EC2 > Instance > Click on your instance > Note down Public IPv4 address`
8. Now open your webbrowser and try to access your website with **http** protocol by typing `http://ip-address`

## Authors

- [@Nav-J](https://github.com/nav-j/)
