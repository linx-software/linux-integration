# Linux / Linx Integration

## Description
Using PuTTY (https://www.putty.org/) you can set up a complete management system in Linx to manage your Linux server / machine. The idea is to use 2 command-line tools provided by PuTTY to make the calls to the Linux machine.

## Installation
### Pre-requisites
- [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) (Specifically, plink.exe and pscp.exe)
    - plink.exe: used to make script or command calls on the Linux machine
    - pscp.exe: user to copy file to and from the Linux machine


### Register Linux machine signature
**First Important step!** You need to register your Linux machine's signature on your Linx machine, in order for the commandline tools to work. To do this, follow these steps:

1. Run the PuTTY Desktop app
1. Type in your Linux machines location (IP Address or Host name)
1. Click "Open"
1. PuTTY will ask whether you trust the host signature. Confirm it.
1. Close PuTTY (Now your commandline tools will accept your Linux signature)

### Configure Solution Settings.

1. Open "LinuxManager.lsoz" in your Linx Designer
1. Click on "Settings" and provide your details for each of the settings
- LinuxConnection: This is the IP or Hostname of your Linux Machine
- UserName: Your user on the Linux machine with sufficient rights
- Password: Your Linux user's password
- PLinkPath: The full path to the plink.exe file
- PSCPPath: The full path to the pscp.exe file


## Usage

### Copy File From Linux
Description: This function will allow you to copy a file from Linux to your Linx machine (Windows)

Usage:

1. Select the function "CopyFileFromLinux" and click "Debug"
2. Provide the Debug Values:
- LocalFullFilePath: The path of where you want to save the file, as well as the file's name when saved.
- ServerFullPath: The path of the file on the Linux machine, including the files name and extension.
3. Click "Run"
4. Your file should now be copied to your local path.

### Copy File To Linux
Description: This function will allow you to copy a file from your local machine to your Linux machine.

Usage:

1. Select the function "CopyFileToLinux" and click "Debug"
2. Provide the Debug Values:
- LocalFullFilePath: The path of the local file you want to copy to Linux. It needs to include the file name and extension.
- ServerFullPath: The path on the Linux machine to where you want to copy the file. Also include the file's full name
3. Click "Run"
4. Your file should now be copied to your Linux machine.

### Run Command on Linux
Description: This function will allow you to run a Linux Command on the Linux Machine, and get the feedback as a Result.

Usage:

1. Select the function "RunCommand" and click "Debug"
2. Provide the Debug Values:
- Command: This is the Linux Command you want to run on the Linux machine. (i.e. "ls /MyFolder" will list the files in the root folder called MyFolder) 
3. Click "Run"
4. The command will run on the Linux machine and you will be provided with the Result

### Run Script on Linux
Description: To perform more complex commands on Linux, you can create a script file (.sh) on Linux and run it via this function. Included in this repo is a small script called "test.sh" to test this function with.

Usage:

1. Select the function "RunScript" and click "Debug"
2. Provide the Debug Values:
- PathToScriptOnServer: The path of the script you want to run on the Linux machine. 
- Parameters: These are any additional parameters that your script might expect.
3. Click "Run"
4. Your script will run and you will receive and outputted results from the script.

## Contributing

For questions please ask the [Linx community](https://linx/software/community) or use the [Slack channel](https://linxsoftware.slack.com/archives/C01FLBC1XNX). 

## License

[MIT](https://github.com/linx-software/template-repo/blob/main/LICENSE.txt)