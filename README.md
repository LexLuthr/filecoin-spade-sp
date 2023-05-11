## Spader
Spader is a simply utility to allow Filecoin SPs to manage the offline deal data download. This utility is stateful and offers a resumption on restart.

### key Features
1. Does not submit a deal to Boost (can be added as optional later)
2. Creates a list of completed downloads based on deal UUID. Makes easy to import in Boost 
3. Uses aria2 for download 
4. Spawns and control its own aria2 daemon 
5. Resumes download after restart 
6. Takes disk space into account (calculated based on piece size)
7. User can define how many deals they want to process in parallel. It will keep working at full capacity till the storage is full

## Pre-requisites
User must have aria2 CLI installed on the server where they wish to run this utility.
The aria2p python package needs to be installed

```shell
pip install aria2p
```

## Importing deals
Once the download is completed, the program will write deal UUID and the corresponding `.car` file name to `<download directory>/completed`