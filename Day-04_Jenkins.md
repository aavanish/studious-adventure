# Install and run Jenkins

1. Create a VM 
2. Copy paste these commands from JEnkins documentation:
```
sudo apt update
sudo apt install fontconfig openjdk-21-jre
java -version
```
then, Jenkins Installation kit
```
sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt update
sudo apt install jenkins
```
Once Jenkins is installed
check
```
systemctl status Jenkins 
```
it should showcase *active* in green color
if not enabled
```
systemctl enable jenkins
```
3. GO to EC2 > Security > Edit Inbound Rules > ADD port 8080

copy URL of your EC2 instance and paste in the new tab of your browser:
```
<Public IP>:8080
```
then in command line :
```
cat /var/lib/jenkins/secrets/initialAdminPassword
```
(for initial jenkins pswrd) and paste it in browser.
4. Create the admin credentials

# Good Work
# Now you are inside JENKINS UI
