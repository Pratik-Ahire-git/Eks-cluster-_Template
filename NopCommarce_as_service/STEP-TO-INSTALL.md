# install Dotnet
sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-8.0

# Create a nop user 

sudo useradd -m -d /var/lib/nopCommerce nop

# install the application and unzip the file

cd /tmp/nopCommerce

sudo wget https://github.com/nopSolutions/nopCommerce/releases/download/release-4.70.5/nopCommerce_4.70.5_NoSource_linux_x64.zip

sudo unzip nopCommerce_4.70.5_NoSource_linux_x64.zip

# create 2 folder

sudo mkdir bin
sudo mkdir logs

# mv the unzip file to /var/lib/

sudo mv /tmp/nopCommerce/ /var/lib

#  Create a service file 

sudo vi /etc/systemd/system/nopCommerce.service

# ensble and start the nop.Commarce.service

     sudo systemctl daemon-reload
     sudo systemctl status nopCommerce.service
     sudo systemctl enable nopCommerce.service
     sudo systemctl start nopCommerce.service
     sudo systemctl status nopCommerce.service