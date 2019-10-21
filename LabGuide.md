## Slide 1 @title[Platform Build MAX Lab WIN]
## <span class="gold"   >UEFI & EDK II Training</span>

Platform Build Lab MinnowBoard Max - Windows 

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>

---
## Slide 2 @title[Lesson Objective]

### <p align="left"<span class="gold"   >Platform Build Labs </span></p>
<span style="font-size:0.9em">Lab Setup and Build for Minnowboard Max/Turbot</span> <br>
<br>

- Hardware Setup for MinnowBoard Max/Turbot 
- Build a EDK II Platform using MinnowBoard  
  Max/Turbot 


## Slide 3 @title[Setup MAX HW Section]
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Platform HW Setup</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Setup hardware for MinnowBoard Max/Turbot </span>

## Slide 4 @title[MAX/Turbot HW]
### <p align="left"><span class="gold" >EDK II Platform (MinnowBoard MAX/Turbot 
Intel<sup>&reg;</sup> Atom processor E3800 Series<br> &lpar;Formerly Bay Trail-I&rpar;

This lab shows the build process for an actual platform – Minnowboard.org

- Using Tianocore source
- Open source EDK II plus open source binary obj. packages

## Slide 5 @title[Workshop Lab Hardware]
### <p align="left"><span class="gold" >MinnowBoard  MAX Workshop Lab Hardware</span></p>


**Warning do not use any other power supply than 5V or the board will Fry


## Slide 6  @title[Instructions for Lab Materials]
### <p align="left"><span class="gold" >Instructions for Lab Materials</span></p>
Directory C:\PlatformBuildLab2_FW\FW\PlatformBuildLab

- FTDI Driver for Serial UART Cable (COM Port) http://www.ftdichip.com/FTDrivers.htm 

- TeraTerm (terminal software for COM Port)https://en.osdn.jp/projects/ttssh2/releases/


## Slide 7 @title[Setup MinnowBoard Max Test System]
<p style="line-height:85%" align="left"><span class="gold" > <b>Setup MinnowBoard Max Test System</b> 

- Hardware:
  - System Under Test (SUT) – MinnowBoard Max
  - USB to 3.3V TTL Cable  (6 pin to USB Type A)
  -  5V power supply

- Connect the USB w/ 6 pin header to SUT (MAX)

- Connect the USB Type A connector to Host (Laptop)

- On your Host  Go to the “Device Manager” in the control panel. 

- Under the "Other devices" category you will see a yellow   !   with a warning icon next to it. 


- You may already have this driver installed if you do not see a  !  warning under “Other devices”


## Slide 8  @title[Setup COM port on Host]
<p style="line-height:80%" align="left"><span class="gold" > <b>Setup COM port on Host</b> 

- Right click yellow   !  and select "Update Driver Software“ from the Device Manager menu 
- Select "Browse my computer for driver software”.
- Click the Browse  button. – Click on “Include subfolders”
- Browse to the location of the folder you unzipped earlier for the FIDI driver.
- Click on the folder and press OK.
- Press Next.  
- Driver will be installed




## Slide 9 @title[Setup TeraTerm]
<p style="line-height:80%" align="left"><span class="gold" > <b>Setup TeraTerm</b> 

- Unzip and Install TeraTerm
- Open TeraTerm Software
- Select the serial port assigned 

- Go to Setup- Serial Port and set the following:
  - Baud: 115200
  - Parity: None
  - Data Bits: 8
  - Stop Bits: 1
  - Flow Control: Xon/Xoff



## Slide 10 @title[Power on MinnowBoard MAX]
<p style="line-height:80%" align="left"><span class="gold" > <b>Power on MinnowBoard MAX</b> 

- Connect the Power supply cable to the MinnowBoard  MAX
- MinnowBoard MAX should boot to the UEFI Shell in the TeraTerm window.

---
## Slide 11 @title[End of Section]
<br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;End of Lab </span>

---
## Slide 12 @title[Lab 3 -Build Max/Turbot Section]
<br><br><br><br><br>
## <p align="left"><span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Build MinnowBoard Turbot</span></p>


## Slide 13 @title[MAX/Turbot HW]
### <p align="left"><span class="gold" >EDK II Platform (MinnowBoard MAX/Turbot 


-  Intel® Atom processor E3800 Series  (Formerly Bay Trail-I)



## Slide 14 @title[MinnowBoard MAX/ Turbot Platform]
<br>
<p align="left"><span class="gold" ><b>Where to get Open Source<BR> MinnowBoard Max</b></span></p>


- Open Source <a href="https://github.com/tianocore/tianocore.github.io/wiki/MinnowBoardMax">Max Development Wiki</a> 
- How to Download  & Build: <a href="https://github.com/tianocore/edk2-platforms/blob/master/Platform/Intel/Vlv2TbltDevicePkg/Readme.md">Readme.md</a> 

Note:
- Step by step if NOT downloading Lab release of Minnowboard MAX/Turbot 


## Slide 15 @title[Download MinnowBoard MAX Lab Source]
### <p align="left"><span class="gold" >Download MAX Lab Source</span></p>
- Download the PlatformBuildLab2_FW.zip from : <a href="https://github.com/tianocore-training/PlatformBuildLab2_FW/archive/master.zip">github.com PlatformBuildLab_FW.zip</a>
<br>
OR<br>
- Use <font face="Consolas">git clone</font> to download the PlatformBuildLab2_FW

```
$ git clone https://github.com/tianocore-training/PlatformBuildLab2_FW.git
```

- Directory PlatformBuildLab_FW will be created

```
   FW 
    - PlatformBuildLab
       - asl         - Asl Compiler 
       - FTDI-Driver - Serial / USB cable 
       - MaxWS       - Minnowboard Max Source 
	   - TeraTerm    - Terminal app
```




## Slide 16 @title[Preparing to Build]
<p align="left"><span class="gold" > <b>Preparing to Build  </b>
</p>

- Directory <font face="Consolas">C:\PlatformBuildLab2_FW\FW\PlatformBuildLab</font> from Download or zip

- Copy \asl Folder to C:\
- Note: Download  Asl compiler as described in the Readme.txt

## Slide 17 @title[Get the Minnowboard Max Source]
<p align="left"><span class="gold" > <b>Copy Minnowboard Max Source  </b>

- Open a VS Command prompt  
- Create a working  space source directory under the home directory<br>
  C:\> mkdir FW
- From the FW/PlatformBuildLab folder, copy and paste folder “..FW/MaxWS” to C:/FW/MaxWS




## Slide 18 @title[Platform Source Directory Structure]
<p align="left"><span class="gold" > <b>Platform Source Directory Structure   </b>
<br>
./MaxWs/ <br>&nbsp;&nbsp;
	edk2/<br>&nbsp;&nbsp;&nbsp;&nbsp;
       <font face="Arial">&lpar;EDK II common packages&rpar;)<br>&nbsp;&nbsp;&nbsp;&nbsp;
		BaseTools/<br>&nbsp;&nbsp;
	edk2-platforms/<br>&nbsp;&nbsp;&nbsp;&nbsp;
       Platform/Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
		   Vlv2TbltDevicePkg /<br>&nbsp;&nbsp;&nbsp;&nbsp;
 	   Silicon/Intel/<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Vlv2DeviceRefCodePkg/<br>&nbsp;&nbsp;
	edk2-non-osi/<br>&nbsp;&nbsp;
	nasm/ &ast;&ast;<br>&nbsp;&nbsp;
	openssl/ &ast;&ast;<br>&nbsp;&nbsp;



Note:
-  Platform Source Directory Structure
   -  Build from ../MaxWs/edk2  directory

---
## Slide 19 @title[Steps to Build & Install Firmware]
<p align="left"><span class="gold" > <b> Steps to Build & Install Firmware </b>)</span><span style="font-size:0.75em;" >  </span></p>
<br>
<ul style="list-style-type:none; line-height:0.95;">
  <li><span style="font-size:01.18em"> <font color="gray"> &#10102;</font>&nbsp; At VS prompt CD to <font face="Consolas">C:/FW/MaxWS</font>  </span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10103;</font>&nbsp; Set up local build environment </span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10104;</font>&nbsp; Invoke <font face="Consolas">"Edksetup Rebuild" (build BaseTools)</font> </span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10105;</font>&nbsp; Invoke the build process (DEBUG & RELEASE) </span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10106;</font>&nbsp; Locate build output (.cap files for BIOS image)</span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10107;</font>&nbsp; Flash capsule image onto the platform</span></li>
  <li><span style="font-size:01.18em"> <font color="gray"> &#10108;</font>&nbsp; Reset & boot new firmware to UEFI Shell</span></li>
</ul>

<br>
<br>
<br>
<i><b>Next slides will follow the above steps</b></i>

 

## Slide 20 @title[Open a VS Command Prompt]
<p align="left"><span class="gold" > <b>Open a VS Command Prompt</b> 
- Follow Steps from <a href="https://gitpitch.com/tianocore-training/Platform_Build_Win_Emulator_Lab/master#/2">here</a> to Pin the Visual Studio Command Prompt to the Windows Task Bar <br>
<br><font color="gray"> &#10102;</font>&nbsp;&nbsp;Open a Visual Studio Command Prompt & <br><br>


```
  > cd C:/FW/MaxWS 
```



## Slide 21 @title[Setup the Build Environment]
<p align="left"><span class="gold" > <b>Setup the Build Environment</b> 
<br><font color="gray"> &#10103;</font>&nbsp;&nbsp;
Run Setenv.bat or type the following: (assumes Python3.7.2 installed)

```
$> setenv.bat


 set WORKSPACE=%CD%
 set PACKAGES_PATH=%WORKSPACE%\edk2;%WORKSPACE%\edk2-platforms\Silicon\Intel;%WORKSPACE%\edk2-platforms\Platform\Intel;%WORKSPACE%\edk2-non-osi\Silicon\Intel

 set EDK_TOOLS_PATH=%WORKSPACE%\edk2\BaseTools
 path=%WORKSPACE%\openssl;%USERPROFILE%\AppData\Local\Programs\Python\Python37-32;%path%
 set NASM_PREFIX=%WORKSPACE%\nasm\
```

Check if Python okay

```
$>  python --version
Python 3.7.2
 
```

   Note: Download Nasm compiler and Openssl described in each of the Readme.txt files 


## Slide 22 @title[Invoke Edksetup]
<p align="left"><span class="gold" > <b>Invoke Edksetup</b> 
<br><font color="gray"> &#10104;</font>&nbsp;&nbsp;
Invoke Edksetup from edk2 directory

```
$> cd edk2
$> Edksetup Rebuild
```


## Slide 23 @title[Platform Build Scripts]
<p align="left"><span class="gold" > <b>Platform Build Scripts</b> 

### Platform Pre & Post Build Scripts<br>
- Many Platforms have a bash, bat  or Python script file to pre or post process the EDK II build process

- For MinnowBoard Max :
### Pre build processing:
- Python script Vlv2TbltDevicePkg/PreBuild.py – determines date and creates BiosId.bin in build output directory

### Post build processing: 
- Python script Vlv2TbltDevicePkg/Feature/Capsule/GenerateCapsule/ GenCapsuleAll.py – creates .CAP files for updating




Note:

For the platform edk II builds usually a script is called that will do pre and post build processing.  
There is also this capability that is part of the .dsc but many developers have not taken advantage of this feature


## Slide 24 @title[Build Process for DEBUG]
<p align="left"><span class="gold" > <b>Build Process for DEBUG Target</b> 
<br><font color="gray"> &#10105;</font>&nbsp;&nbsp;

- From the edk2 directory invoke the “build” command to build MinnowBoard Max
- Note: Use the Your VS TAG below with “-t” option

```
 $ cd C:\FW\MaxWS\edk2
 $ build -a IA32 -a X64 -t VS2015x86 -p Vlv2TbltDevicePkg\PlatformPkgX64.dsc –y Vlv.report -v
```


### <b>NOTE: Press Enter to Continue the build</b>


## Slide 25 @title[Examine Command Line & Build Parameters]
<p align="left"><span class="gold" > <b>Examine Build Parameters</b></span></p> 




```
 $ cd C:\FW\MaxWS\edk2
 $ build -a IA32 -a X64 -t VS2015x86 -p Vlv2TbltDevicePkg\PlatformPkgX64.dsc –y Vlv.report -v
```



<br>
<table id="recTable">
	<tr class="fragment">
		<td align="left"  height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>TARGET</b></span></p></td>
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>= DEBUG</b></span></p></td>
		<td align="left" bgcolor="gray" height=".0025"><p style="line-height:010%"><span style="font-size:0.96em" ><b>Build Mode </b>(default) </td>
	</tr>
	<tr class="fragment">
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>TARGET_ARCH</b></span></p></td>
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>= IA32 X64</b></span></p></td>
		<td align="left" bgcolor="gray" height=".0025"><p style="line-height:010%"><span style="font-size:0.96em" ><b>CPU Architecture</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>TOOL_CHAIN_TAG</b></span></p></td>
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>= VS2013x86</b></span></p></td>
		<td align="left" bgcolor="gray" height=".0025"><p style="line-height:010%"><span style="font-size:0.96em" ><b>VS Tool Chain</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>ACTIVE_PLATFORM</b></span></p></td>
		<td align="left"   height=".0025"><p style="line-height:080%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>=Vlv2TbltDevicePkg /PlatformPkgX64</b></span></p></td>
		<td align="left" bgcolor="gray" height=".0025"><p style="line-height:010%"><span style="font-size:0.96em" ><b>MAX Platform DSC file</b></span></p></td>
	</tr>
	<tr class="fragment">
		<td align="left"   height=".0025"><p style="line-height:088%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>Report File Created</b></span></p></td>
		<td align="left"   height=".0025"><p style="line-height:010%"><span style="font-size:0.9460em; font-family:Consolas; " ><b>= Vlv.report</b></span></p></td>
		<td align="left" bgcolor="gray" height=".0025" width="35%"><p style="line-height:080%"><span style="font-size:0.96em" ><b>PCDs, Libs, etc. . .</b></span></p></td>
	</tr>
</table>

---
## Slide 26 @title[Examine Platform Parameters]
<p align="left"><span class="gold" > <b>Platform Build and PCD Parameters</b> </span></p>

### Platform Parameters<br>
- Many Platform Parameters are defined in  a top .DSC file that controls  PCD and build switches

### PlatformPkgConfig.dsc <br>
Example:

```xml
 #
 # TRUE is ENABLE. FALSE is DISABLE.
 #
  //  . . .
 DEFINE SECURE_BOOT_ENABLE = TRUE
 DEFINE USER_IDENTIFICATION_ENABLE = FALSE
 DEFINE VARIABLE_INFO_ENABLE = FALSE
 DEFINE S3_ENABLE = TRUE
 DEFINE CAPSULE_ENABLE = TRUE
 DEFINE CAPSULE_RESET_ENABLE = TRUE
  // . . .

```

Note:

many will have "ifdef" statements in the major .dsc file in order to enable a feature or not


## Slide 27 @title[Build Process for Release]
<p align="left"><span class="gold" > <b>Build Process for RELEASE Target</b> </span></p>
<br><font color="gray"> &#10105;</font>&nbsp;&nbsp;Release build

- Note: Use the Your VS TAG below with “-t” option

From VS Prompt enter:
```
$ cd MaxWS/edk2
$ build -a IA32 -a X64 -t VS2015x86 -b RELEASE -p Vlv2TbltDevicePkg\PlatformPkgX64.dsc -v
```


## Slide 28 @title[DEBUG & RELEASE Differences]
### DEBUG & RELEASE Differences

- Slower boot because the time it takes to display debug info
- Larger image because of debug code & embedded info
- Uses the serial port for debug string output
- Contains detailed debug strings that show 
the boot process and various ASSERT/TRACE errors


### DEBUG build …
- Contains detailed debug strings that show the boot process, along with various ASSERT/TRACE errors
- Uses the serial port for debug string output
- Larger image than RELEASE, due to the embedded debug info
- Slower boot than RELEASE, due to the time it takes to display the debug info


### RELEASE build …
- Does not contain the debug strings
- Does not use the serial port for debug output
- Smaller image than DEBUG
- Faster boot than DEBUG


## Slide 29 @title[Build Process Completed]
<p align="left"><span class="gold" > <b>Build Process Completed</b> </span></p>

Locate the build .Cap images

The platform post build process will create capsule images to use with a capsule update process<br>
<br>
The script displays the location of the final .cap files

Note:
- The EDK II build generates multiple firmware volumes, which are combined in the .BIN image
- typically the platform script will call a stitching process to combine all the images together in  post processing after the EDK II build

for the the MinnnowBoard Capsule files are created to use withthe CapsuleApp.efi application


## Slide 30 @title[Flash onto the MinnowBoard MAX]
<p align="left"><span class="gold" > <b>Flashing the New Firmware</b></span></p> 



1. Access Max .CAP files from build folder
 - . . ./Build/Vlv2TbltDevicePkgX64/Capsules/TestCert_X64_DEBUG_VS2015x86
 - *.cap 
 - RELEASE	. . ./Capsules/TestCert_X64_DEBUG_VS2015x86
2. Copy .cap files to a USB Thumb drive
3. Copy CapsuleApp.efi to a USB thumb drive
4. Boot into the UEFI Shell  on Max then  type “FS0:”



## Slide 31 @title[Flash onto the MinnowBoard MAX 02]
<p align="left"><span class="gold" > <b>Flashing the New Firmware</b> </span></p>

Run CapsuleApp.efi utility with MinnowMax. . . cap file
(Note the “TAB” Key will fill out the command line for you )
```
FS0:\> CapsuleApp.efi MinnowMax.0.0.0.12.cap 
```

System will start the Capsule update process
There will be 2 reboots

## Slide 32 @title[Capsule Update with External Monitor]
<p align="left"><span class="gold" > <b>Capsule Update with External Monitor</b> </span></p>

Logo with a progress bar will display update process progress


Note:

If an external monitor is connected to the system under test 
the monitor will show a progress bar for the capsule update


## Slide 33 @title[Verify after Firmware Update]
<p align="left"><span class="gold" > <b>Verify After Firmware Update</b> </span></p>

Reboot and Verify

- Verify that the Firmware was updated by checking the Date
- At the shell prompt type “exit”
- The EDK II front page will show the BIOS ID with Date/time stamp

---
## Slide 34 @title[Summary]
##### <p align="left"><span class="gold"   >Summary </span></p><br>
Hardware Setup for Minnowboard Max/Turbot <br>
Build a EDK II Platform using Minnowboard 

## Slide 3 @title[Questions]
<br>

---
## Slide 35 @title[return to main]
<p align="left"><span class="gold"   ><b>Return to Main Training Page</b> 
<br>
<br>

## Slide 36 @title[Logo Slide]

---
## Slide 37 @title[Acknowledgements]
#### <p align="left"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2019, Intel Corporation. All rights reserved.
**/

```

---
## Slide 39 @title[Backup Section]
<br><br><br><br><br>
## <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Back up</span>
<span style="font-size:0.9em" > &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>

---
## Slide 40 @title[Build Errors]
<br>

### Build Errors

---
## Slide 41 @title[Build Error- RC.exe ]
<p align="left"><span class="gold" ><b>Build Error- RC.exe </b></span></p>
Because RC.Exe is not found, Error Message:<br>

```
   "c:\Program Files (x86)\Windows Kits\8.0\bin\x64\rc.exe" 
/Foc:\edkii.svn\Build\NT32IA32\DEBUG_VS2013x86\IA32\MdeModulePkg\Application\HelloWorld\HelloWorld\OUTPUT
\HelloWorldhii.lib 
c:\edkii.svn\Build\NT32IA32\DEBUG_VS2013x86\IA32\MdeModulePkg\Application\HelloWorld\HelloWorld\OUTPUT\He
lloWorldhii.rc
'c:\Program' is not recognized as an internal or external command,
operable program or batch file.
 
NMAKE : fatal error U1077: '"c:\Program Files (x86)\Windows Kits\8.0\bin\x64\rc.exe' : return code '0x1'
Stop.

```

Find where the RC.EXE is located on your VS Installation:  </span></p>

Example (VS 2013):  The RC.exe is located on this machine: <br>

```
C:\Program Files (x86)\Windows Kits\8.1\bin\x64
Edit `Conf/tools_def.txt` 
```

## Slide 42 @title[Build Error- RC.exe 02]
<p align="left"><span class="gold" ><b>Build Error- RC.exe Cont...</b></span></p>
<br>
Search for your installation of Visual Studio (2013 or 2015)<br>
Update according to the path for where the RC.EXE is found 

```
# Microsoft Visual Studio 2013 Professional Edition
DEFINE WINSDK8_BIN       = c:\Program Files\Windows Kits\8.1\bin\x86\
DEFINE WINSDK8x86_BIN    = c:\Program Files (x86)\Windows Kits\8.1\bin\x64
 
# Microsoft Visual Studio 2015 Professional Edition
DEFINE WINSDK81_BIN       = c:\Program Files\Windows Kits\8.1\bin\x86\
DEFINE WINSDK81x86_BIN    = c:\Program Files (x86)\Windows Kits\8.1\bin\x64

```

---
## Slide 43 @title[Build Error- C1041 ]
<p align="left"><span class="gold" ><b>Build Error: fatal error C1041: </b></span></p>
- Build Error from fatal error C1041: cannot open program database

- This Error is usually because the location you are building is being shared by another application in Windows.  Example: Syncplicity may cause this


Error Message:

```
k:\fw\edk2\MdePkg\Library\BaseLib\LinkedList.c : fatal error C1041: cannot open program 
database 
'k:\fw\edk2\build\nt32ia32\debug_vs2013x86\ia32\mdepkg\library\baselib\baselib\vc120.pdb'; if 
multiple CL.EXE write to the same .PDB file, please use /FS
NMAKE : fatal error U1077: '"C:\Program Files (x86)\Microsoft Visual Studio 
12.0\Vc\bin\cl.exe"' : return code '0x2'
Stop.

```

<b>Solution:</b>  Try using a Workspace that is not shared
