# Immich For MM

## 1. Install Docker
Use the instructions on [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)

## 2. Configure Docker
Allow the primary, non-root user to access Docker: [https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)

## 3. Download Immich Files
Open a terminal and navigate the directory that will store the files needed to run Immich.  Run the following command to download the files to get started. 

```bash
git clone https://github.com/ManzellaTech/immich-for-mm.git
```

## 4. Edit Immich Configuration Files

Still in the terminal run the following command to navigate to Immich's configuration files:
```bash
cd immich-for-mm
```

Use a text editor (such as vim or nano) to edit the `.env` file (hidden by default).  Change the variables below.  

### Set Path To Photos
`EXTERNAL_LIBRARY_LOCATION` variable should changed to the path of your photos.  

### Set New Database Password
`DB_PASSWORD` variable should be changed to a long, strong password using only letters and numbers.  

## 5. Start Docker
Still in the terminal run the following command to start Immich:
```bash
docker compose up -d
```
This may take several minutes as Docker downloads the images it needs and starts them.  

## 6. Log into Immich
In a web browser, navigate to [http://localhost:2283](http://localhost:2283).  Go through the setup wizard and create the Immich admin account.  

## 7. Add Photos Directory
In Immich:
- Click on your avatar in the upper right corner
- Click on `Administration` -> `External Libraries`
- Click on `Create an external library`...
- Select which user owns the library, this can not be changed later
- Enter `/images_external_library` then click `Add`
- Click on `Save`
- Click the drop-down menu on the newly created library
- Click on `Scan`
This may take a long time and lot of resources as Immich starts pulling in metadata and generating thumbnails.  