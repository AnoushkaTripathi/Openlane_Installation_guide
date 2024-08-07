# Openlane_Installation_guide

![image](https://github.com/user-attachments/assets/64ce5674-3e3d-492f-bde6-abcda1b12f40)

Installing Docker

![image](https://github.com/user-attachments/assets/fae438f8-7808-4c2c-854c-f3d22768f791)

```
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```
```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```
Verify that the Docker Engine installation is successful by running the hello-world image.

```
sudo docker run hello-world
```
The "permission denied" error when trying to connect to the Docker daemon socket at unix:///var/run/docker.sock typically indicates that your user does not have the necessary permissions to access the Docker socket. This can happen when you are not part of the `docker` group, or if the Docker service is not running.

Here are the steps to resolve this issue:

### 1. Add Your User to the Docker Group

1. **Create the Docker group**:
    ```sh
    sudo groupadd docker
    ```

2. **Add your user to the Docker group**:
    ```sh
    sudo usermod -aG docker $USER
    ```




## Installing Openlane
![image](https://github.com/user-attachments/assets/72e77a69-5a24-42ed-9a6f-c6723a7d2005)

Make sure you have required packages for openlane installation
```
git --version
docker --version
python3 --version
python3 -m pip --version
make --version
python3 -m venv -h
```
Update the package database and upgrade the packages to avoid version mismatches then install required packages as follows:
```
sudo apt-get update
sudo apt-get upgrade
sudo apt install -y build-essential python3 python3-venv python3-pip python3-tk curl make git
```

```
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```
