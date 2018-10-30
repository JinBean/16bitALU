# Step-by-step instructions for windows:

### Xilinx ISE

	• https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/design-tools.html
	• Select 14.7 at side panel and scroll down to ISE Design Suite
	• Create and verify your account
	• Download and extract folder and double click on xsetup to being installation
	• In the meantime, go to http://www.xilinx.com/getlicense 
	• Log in and select ISE WebPACK License and click on "Generate Node-Locked License"
	• Click on "Next" twice and it should dowload a license file
	• Create a folder named ".xilinx." in the root directory of  where you installed Xilinx
		○ Must add both full stops (important)
		○ Windows will automatically remove the back
	• Put the license file into the .xilinx folder
	• When Xilinx is done downloading, navigate to /Xilinx/14.7/ISE_DS/ISE/bin/nt
	• Copy "ise.exe" 
	• Navigate to /Xilinx/14.7/ISE_DS/ISE/bin/nt64 and rename the "ise.exe" in that folder to "ise64.exe"
	• Paste the previously copied "ise.exe" to the nt64 folder
	• Running the new "ise.exe" should start up the Xilinx ISE


### MojoLoader

	• https://alchitry.com/pages/mojo-loader
	• Download Windows Installer
	• Run "mojo-loader.exe"


### MojoIDE

	• https://alchitry.com/pages/mojo-ide
	• Download Windows Installer (exe)
	• Hammer icon is to build project
	• First time building project:
		○ Navigate to /Xilinx/14.7/ISE_DS/PlanAhead/bin
		○ Edit planAhead.bat file with notepad
		○ Add "-m32" to the back of the last line of the file
	• Hollow arrow is for uploading to the Mojo RAM, code will be wiped when power is off
	• Filled arrow is for uploading to Mojo's flash memory, and will automatically load up when the board is powered on



Both MojoLoader and MojoIDE require Xilinx to run, but they are independent of each other

MojoLoader is for reading .bin files that are created outside MojoIDE
