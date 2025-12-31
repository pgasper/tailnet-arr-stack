# **tailnet-arr-stack**

This repository contains everything you need to create your own Jellyfin media server with Sonarr, Radarr, Jellyseerr, Prowlarr, Jackett, qBittorrent, and Gluetun (VPN) in a Docker Compose setup.

## **Table of contents**

- [**tailnet-arr-stack**](#tailnet-arr-stack)
  - [**Table of contents**](#table-of-contents)
    - [**Jellyfin**](#jellyfin)
    - [**Jellyseerr**](#jellyseerr)
    - [**Sonarr**](#sonarr)
    - [**Radarr**](#radarr)
    - [**Jackett**](#jackett)
    - [**Flaresolverr**](#flaresolverr)
    - [**Prowlarr**](#prowlarr)
    - [**qBittorrent**](#qbittorrent)
    - [**Gluetun (VPN)**](#gluetun-vpn)
- [**Prerequisites**](#prerequisites)
  - [**Docker**](#docker)
    - [**Using Docker Compose :**](#using-docker-compose-)
- [**VPN**](#vpn)
  - [**PROTON**](#proton)
  - [**Troubleshoot VPN**](#troubleshoot-vpn)
- [**Installation**](#installation)
  - [**1. Basic Installation**](#1-basic-installation)
  - [**4. Installation with VPN**](#4-installation-with-vpn-no-nvidia)
- [**Accessing Applications**](#accessing-applications)
- [**Configuration Guide for Web Interfaces Only**](#configuration-guide-for-web-interfaces-only)
  - [**qBittorrent**](#qbittorrent-1)
    - [**Category Configuration**](#category-configuration)
  - [**Radarr**](#radarr-1)
    - [**Media Management**](#media-management)
    - [**Download Clients**](#download-clients)
    - [**Indexer Jackett (Optional)**](#indexer-jackett-optional)
  - [**Sonarr**](#sonarr-1)
    - [**Media Management**](#media-management-1)
    - [**Download Clients**](#download-clients-1)
    - [**Indexer Jackett (Optional)**](#indexer-jackett-optional-1)
  - [**Prowlarr**](#prowlarr-1)
    - [**Configure Torrent Indexers**](#configure-torrent-indexers)
    - [**Configure FlareSolverr**](#configure-flaresolverr)
    - [**Configure Radarr**](#configure-radarr)
    - [**Configure Sonarr**](#configure-sonarr)
  - [**Jellyfin**](#jellyfin-1)
    - [**Initial Setup**](#initial-setup)
    - [**Adding Users to Jellyfin**](#adding-users-to-jellyfin)
  - [**Jellyseerr**](#jellyseerr-1)
    - [**Sign In / Configuration**](#sign-in--configuration)
    - [**Integrating with Radarr**](#integrating-with-radarr)
    - [**Integrating with Sonarr**](#integrating-with-sonarr)
- [**Updating Applications**](#updating-applications)
- [**Disclaimer**](#disclaimer)


This repository allows you to create your own Jellyfin media server with all the necessary tools to manage your movies, TV shows, music, and eBooks. It also includes tools to automate the downloading of new content and to protect your privacy using a VPN.

> [!IMPORTANT]  
> To use Docker Compose, make sure Docker is installed on your system.

---

### **Jellyfin**

[Jellyfin](https://jellyfin.org/) is an open-source media server software that allows you to stream your movies, TV shows, music, and eBooks to all your devices. It is compatible with many types of media files and supports streaming to numerous devices.

### **Jellyseerr**

[Jellyseerr](https://github.com/Fallenbagel/jellyseerr) is an open-source application that allows you to automate the management of your Jellyfin media server. It works by monitoring your Jellyfin library and automatically searching for and downloading new content based on your preferences. Jellyseerr supports integration with various other tools, such as Sonarr and Radarr, to provide a seamless experience for managing your media collection.

### **Sonarr**

[Sonarr](https://sonarr.tv/) is TV show management software that allows you to search, download, and manage your favorite TV shows automatically. It works with many types of trackers and torrent clients and supports automatic subtitle downloading.

### **Radarr**

[Radarr](https://radarr.video/) is movie management software that allows you to search, download, and manage your favorite movies automatically. It works with many types of trackers and torrent clients and supports automatic subtitle downloading.

### **Jackett**

[Jackett](https://github.com/Jackett/Jackett) is a proxy software for torrent trackers that allows you to search for torrent files on many trackers from one place. It works with many types of torrent clients and supports authentication and advanced searching.

### **Flaresolverr**

[Flaresolverr](https://github.com/FlareSolverr/FlareSolverr) is open-source software that allows you to bypass streaming restrictions on video-sharing sites. It works by resolving streaming links and bypassing geographical blocks and playback restrictions.

### **Prowlarr**

[Prowlarr](https://github.com/Prowlarr/Prowlarr) is download management software that allows you to search for and automatically download files from many types of sources, including torrent trackers, newsgroups, and direct download sites.

### **qBittorrent**

[qBittorrent](https://www.qbittorrent.org/) is open-source BitTorrent client software that allows you to download torrent files. It is lightweight, easy to use, and supports many advanced features such as built-in torrent search, encryption, torrent creation, and support for private trackers.

### **Gluetun (VPN)**

[Gluetun](https://github.com/qdm12/gluetun) is open-source VPN client software that allows you to connect to VPN servers. It is easy to use and supports many advanced features such as port forwarding, DNS leak protection, and support for multiple VPN protocols.

---

# **Prerequisites**

> [!NOTE]  
> This service requires a machine with at least 4 CPU cores and 8 GB of RAM. 

## **Docker**

To install Docker on your system, follow the install instructions on docker website for your system.

> [!TIP]
> I recommend giving Docker administrative rights to your user:
> ```bash
> usermod -aG docker <user>
> ```
> After this command, disconnect and reconnect.


### **Using Docker Compose :**

To use Docker Compose with this repository, you first need to choose whether you want to use the version with VPN or without VPN. Then, navigate to the corresponding directory (with-vpn or without-vpn) and run the following command :

```bash
docker-compose up -d
```
To shut down the stack :

```bash
docker-compose down
```

**[`^        back to top        ^`](#table-of-contents)**

## **NVIDIA**
For setup with Nvidia:
https://www.youtube.com/watch?v=OF_5EKNX0Eg

# **VPN**
## **PROTON**

Go to [Protont VPN](https://account.protonvpn.com/downloads) website.

1. Go to Download :

2. Configure your VPN manually with an OS name to use, and make sure to enable NAT-PMP. Finally, select the desired country :

3. You can now gather your information for the Gluetun container setup :

> [!CAUTION]  
> Make sure you have either downloaded the file or copied its content into a text file, as some information will no longer be available after you click "Close".

## **Troubleshoot VPN** 

Once the Docker is launched, you can test your VPN with the following command :

```bash
docker exec qbittorrent curl -s https://api.ipify.org/
# Result
94.101.115.63
```

# **Installation**

First, clone the repository :

```bash
git clone https://github.com/pgasper/tailnet-arr-stack
cd tailnet-arr-stack/
```

For the installation, I have only created one version of the `docker-compose` file.

Before proceeding, navigate to the `.env` file located in the root directory and complete it with the required information. This file must always be at the root of the `docker-compose` file you are going to launch.

```yaml
# BASE
COMMON_PATH=/some/path Set this to some path on your PC/Server where you want to save config files and downloads from qbit

TZ=Europe/Ljubljana

# Uncomment the lines below to enable VPN

# PROTON VPN 
# ENDPOINT_IP=PEER_ENDPOINT_IP  # The endpoint IP address of the VPN server
# WIREGUARD_ADDR=Interface_Address  # The WireGuard interface address
# ENDPOINT_PORT=51820  # Default port is 51820, but confirm if different
# DNS_ADDRESS=Interface_DNS  # DNS address for ProtonVPN
# PUBLIC_KEY=PEER_PublicKey  # The public key of the other peer
# PRIVATE_KEY=Interface_PrivateKey  # Your private key
```

> [!WARNING]  
> Make sure you uncomment and configure the settings according to the VPN service you're using. This step is essential for establishing a proper VPN connection.

## **1. Installation with VPN**

> [!WARNING]  
> If you use this method, fill in the `.env` file located.

Standard installation with a `VPN`:

To start the installation, execute :

```bash
docker compose up -d
```

**[`^        back to top        ^`](#table-of-contents)**

# **Accessing Applications**

Once the applications are deployed, you can access them using the following addresses :

> [!IMPORTANT]  
> Replace `localhost` with the IP address of your machine or remote server if needed.


* Jellyfin : http://localhost:8096
* Jellyseer : http://localhost:5055
* Sonarr : http://localhost:8989
* Radarr : http://localhost:7878
* Jackett : http://localhost:9117
* Prowlarr : http://localhost:9696
* qBittorrent : http://localhost:8080

Gluetun (Nord VPN) will be automatically configured to be used with the applications.

# **Configuration Guide for Web Interfaces Only**

> [!IMPORTANT]  
> All links containing the container name can be replaced with either the server IP or `localhost`. Also, replace `/COMMON_PATH/` with the path you configured in the `.env` file.


## **qBittorrent**

1. Open the WebUI by clicking on the application icon in the **DOCKER** tab and selecting **WebUI**.
2. Log in with the default credentials:
   - **Username**: `admin`
   - **Password**: `adminadmin` or get password with docker logs qbittorrent

   *Note: The default credentials may have changed, please check the documentation for updates on this. In most cases, qBittorrent Web UI will generate a temporary password when the container is started. To view this password, check the logs for this container with the command: `docker logs qbittorrent`*

1. Once logged in, click the gear icon to go to **Options**.
2. Under the **Downloads** tab, configure the backup settings as follows:
   - **Default Torrent Management Mode**: `Automatic` (required for category-based save paths to work)
   - **When Torrent Category changed**: `Relocate torrent`
   - **When Default Save Path changed**: `Relocate affected torrents`
   - **When Category Save Path changed**: `Relocate affected torrents`
   - **Default Save Path**: `/downloads` 
3. Click **SAVE**.

### **Category Configuration**

1. In the WebUI, expand **CATEGORIES** in the left menu. Right-click on **All** and select **Add category...**.
2. In the **New Category** window, configure as follows:
   - **Category**: `radarr` (this corresponds to the category you will later configure in Radarr)
   - **Save path**: `/downloads/radarr`
3. Click **Add**.
4. Right-click on **All** again, select **Add category...**.
5. Configure as follows:
   - **Category**: `sonarr` (this should match the category configured later in Sonarr, by default `sonarr-tv`, but this guide uses `sonarr`)
   - **Save path**: `/downloads/sonarr`
6. Click **Add**.

**[`^        back to top        ^`](#table-of-contents)**

---

## **Radarr**

### **Media Management**

1. Open the WebUI and go to **Settings** > **Media Management**.
2. Click **Add Root Folder**, add the path `/movies`, and click **OK**.
3. Click **Show Advanced** at the top, scroll down to **Importing**, and make sure **Use Hardlinks instead of Copy** is enabled.

### **Download Clients**

1. In the WebUI, go to **Settings** > **Download Clients**.
2. Click **+** under **Download Clients**, then select **qBittorrent** from the **Add Download Client** window.
3. Fill in the fields as follows:
   - **Name**: `qBittorrent` (or another name of your choice)
   - **Host**: `qbittorrent`
   - **Username**: `admin`
   - **Password**: `adminadmin` (change it if you've modified it in qBittorrent)
   - **Category**: `radarr` (this should match the category set in qBittorrent)
4. Click **Test**. If you see a checkmark, it means the connection is working; if not, there is an error.
5. Click **Save**.

_Note: if entering `qbittorrent` as the Host does not work, try entering the IP address instead (ex: `192.168.x.x`)_

> [!WARNING]
> On new installations, Radarr may complain that the `/downloads/radarr` directory does not exist inside the container (this is generally flagged as an error by Radarr in  **System** > **Status**). To fix this, simply move into the directory `/COMMON_PATH/qbittorrent/downloads` and manually create the `radarr` directory. Then, simply delete qBittorrent from Radarr and re-add it -  you should see the error disappear.

**[`^        back to top        ^`](#table-of-contents)**

---

## **Sonarr**

### **Media Management**

1. Open the WebUI and go to **Settings** > **Media Management**.
2. Click **Add Root Folder**, add the path `/tv`, and click **OK**.
3. Click **Show Advanced**, scroll down to **Importing**, and enable **Use Hardlinks instead of Copy**.

_Note: if entering `qbittorrent` as the Host does not work, try entering the IP address instead (ex: `192.168.x.x`)_

### **Download Clients**

1. In the WebUI, go to **Settings** > **Download Clients**.
2. Click **+** under **Download Clients**, then select **qBittorrent**.
3. Fill in the fields as follows:
   - **Name**: `qBittorrent` (or another name of your choice)
   - **Host**: `qbittorrent`
   - **Username**: `admin`
   - **Password**: `adminadmin` (change it if you've modified it in qBittorrent)
   - **Category**: `sonarr` (this should match the category set in qBittorrent)
4. Click **Test**. If you see a checkmark, it means the connection is working.
5. Click **Save**.

**[`^        back to top        ^`](#table-of-contents)**

---

## **Prowlarr**

### **Configure Torrent Indexers**

1. Open the WebUI and go to **Indexers** > **Add New Indexer**.
2. Select **1337x** (or another tracker of your choice).
   - You can modify the settings as per your preference, but the default values generally work well.
   - Sorting by **Seeders** can be useful for faster downloads.
3. Click **Test**. If you see a checkmark, the connection is functional; otherwise, there's an error.
4. Click **Save**.

### **Configure FlareSolverr**

1. Go to **Settings** and click **+** under **Indexer**.
2. Select **FlareSolverr** and fill in the information as follows:
   - **Name**: `FlareSolverr`
   - **Tags**: `flaresolverr`
   - **Host**: `http://flaresolverr:8191/`
3. Click **Test** to check the connection.
4. Click **Save**.

### **Configure Radarr**

1. Go to **Settings** and click **Apps**.
2. Select **Radarr** and fill in the information as follows:
   - **Sync Level**: `Full Sync`
   - **Prowlarr Server**: `http://prowlarr:9696`
   - **Radarr Server**: `http://radarr:7878`
   - **ApiKey**: Find the API key in the Radarr interface under **Settings** > **General** > **API Key**.
3. Click **Test** to check the connection.
4. Click **Save**.

### **Configure Sonarr**

1. Go to **Settings** and click **Apps**.
2. Select **Sonarr** and fill in the information as follows:
   - **Sync Level**: `Full Sync`
   - **Prowlarr Server**: `http://prowlarr:9696`
   - **Sonarr Server**: `http://sonarr:8989`
   - **ApiKey**: Find the API key in the Sonarr interface under **Settings** > **General** > **API Key**.
3. Click **Test** to check the connection.
4. Click **Save**.


**[`^        back to top        ^`](#table-of-contents)**

---

## **Jellyfin**

### **Initial Setup**

1. Open the Web UI by going to the **DOCKER** tab, click the app logo for Jellyfin, and select **WebUI**.
2. Select a preferred display language (or use the default English). Click **Next** ➝.
3. Create an administrator account, fill out the credentials as desired, and click **Next** ➝.
4. Click **Add Media Library** and fill in the following:
   - **Content type**: Movies
   - **Folders**: `/COMMON_PATH/radarr/movies`
   - Configure the rest as you see fit; the default settings are typically fine.
5. Click **OK**.
6. Click **Add Media Library** again and fill in the following:
   - **Content type**: Shows
   - **Folders**: `/COMMON_PATH/sonarr/tv`
   - Configure the rest as you see fit; the default settings are typically fine.
7. Click **OK**.
8. Click **Next** ➝.
9. Configure the **Preferred Metadata Language** (or use the default), and click **Next** ➝.
10. In **Configure Remote Access**, leave **Allow Remote Connections to this Server** checked and **Enable Automatic Port Mapping** unchecked.
11. Click **Next** ➝, then click **Finish**.
12. Sign in with your administrator account.

Once you sign in, if you already have media in your `/COMMON_PATH/*` folders, it should start appearing in Jellyfin. If not, the content will populate as the folders are filled.

### **Adding Users to Jellyfin**

If you want other users to access your Jellyfin server, you can create additional user accounts. This step is optional if you're the only user.

1. Open the left menu by clicking on the three horizontal lines (hamburger menu) in the upper left corner.
2. Select **Users** and click the **+** button on the left to add a new user.
3. Fill in the following details for the new user:
   - **Name**: `<username>`
   - **Password**: `<password>`
   - Under **Library Access**, check the boxes for the libraries (Movies, TV shows, etc.) that you want the user to have access to.
4. Click **Save** to create the user.
5. Repeat this process for all users you wish to add to the server.

**[`^        back to top        ^`](#table-of-contents)**

---

## **Jellyseerr**

### **Sign In / Configuration**

1. Open the WebUI and in the **Welcome to Jellyseerr** screen, select **Use your Jellyfin account**.
2. Fill in the information as follows:
   - **Jellyfin URL**: `http://jellyfin:8096/`
   - **Email Address**: `<your email address>`
   - **Username**: `<your Jellyfin username>`
   - **Password**: `<your Jellyfin password>`
3. Select **Sign In**.
4. Go to **Sync Libraries** under **Jellyfin Libraries**, select your Jellyfin libraries, then click **Continue**.

### **Integrating with Radarr**

1. Go to **Radarr Settings**, then click **Add Radarr Server**.
2. Fill in the information as follows:
   - **Default Server**: Check this box
   - **Server Name**: `Radarr`
   - **Name or IP Address**: `http://radarr`
   - **Port**: `7878`
   - **API Key**: Find the API key in the Radarr interface under **Settings** > **General** > **API Key**.
3. Click **Test** to check the connection.
4. Click **Save Changes**.

### **Integrating with Sonarr**

1. Go to **Sonarr Settings**, then click **Add Sonarr Server**.
2. Fill in the information as follows:
   - **Default Server**: Check this box
   - **Server Name**: `Sonarr`
   - **Name or IP Address**: `http://sonarr`
   - **Port**: `8989`
   - **API Key**: Find the API key in the Sonarr interface under **Settings** > **General** > **API Key**.
3. Click **Test** to check the connection.
4. Click **Save Changes**.

**[`^        back to top        ^`](#table-of-contents)**

---

# **Updating Applications**

To update the applications, you need to stop the running containers and remove the existing Docker images. You can use the following commands to perform these operations:

```bash
docker-compose down
docker image prune -a
```

Then, you can run `docker-compose up -d` to restart the containers with the latest versions of the applications.

**[`^        back to top        ^`](#table-of-contents)**

# **Disclaimer**

This code is provided for informational purposes only and should not be used for illegal activities. I am not responsible for the actions performed by users of this code. This code is for informational purposes, and if people wish to use it, they should consult the laws of their countries.
