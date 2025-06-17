## From Apt (Ubuntu)

# step 1
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null

# step 2
sudo apt-get install apt-transport-https --yes

# step 3
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list

# step 4
sudo apt-get update

# step 5
sudo apt-get install helm

## verify 

helm version
