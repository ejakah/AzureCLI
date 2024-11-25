# Install Azure CLI
# For Ubuntu/Debian-based systems
# Update your repository information:


`sudo apt-get update`
# Install prerequisites:


`sudo apt-get install -y ca-certificates curl apt-transport-https lsb-release gnupg`
# Download and install the Microsoft signing key:


`curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/microsoft.asc.gpg > /dev/null`
# Add the Azure CLI software repository:


`AZ_REPO=$(lsb_release -cs)`
`echo "deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ $AZ_REPO main" | sudo tee /etc/apt/sources.list.d/azure-cli.list`
# Update repository information again and install the Azure CLI:


`sudo apt-get update`
`sudo apt-get install -y azure-cli`
# 2. Authenticate with Azure
# Log in to Azure:


`az login`
# Follow the instructions to log in via your web browser.

# Log in to your Azure Container Registry:


az acr login --name sentics
# 3. Pull and Run the Docker Image
# Pull the Docker image:


`docker pull sentics.azurecr.io/dashboard-ui:f63b2e3fe606f7a77b9afb1cdb351da3d77aca44`
`docker run -d -p 3100:3100 sentics.azurecr.io/dashboard-ui:f63b2e3fe606f7a77b9afb1cdb351da3d77aca44`

