# 🌀 Devian installation
⚠️ Use the `Command` key on **macOS** or the `Right Ctrl` key on **Ubuntu** to capture your mouse in the virtual machine and vice versa.
<br/>⚠️ To confirm an action, press the **Enter** key, and use the **Arrow** keys to navigate through the options.

# Step 1: Installation Preparation

> ### Select Version Without Graphical Interface.
>> The Born2beroot project requires a command-line-only environment, so choose the version without a graphical interface.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/1.png">

# Step 2: Language and Location Selection

> ### Installation Language.
>> Choose the installation language. The default is English.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/2.png">

> ### Select Country and Continent.
>> Choose your country or, if it’s not listed, use the “Other” option to find the continent and country.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/3.png">

> ### It's time to select a continent.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/4.png">

> ### Now, select your country from the list.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/5.png">

> ### Choose United States.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/6.png">


> ### Keyboard Layout.
>> Select the correct keyboard layout. If you use ANSI, select American English. <br/>
>> If you're unsure about your keyboard layout you can consult [Keyboard layouts](https://keyshorts.com/blogs/blog/44712961-how-to-identify-laptop-keyboard-localization).
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/7.png">

# Step 3: Hostname and User Configuration

> ### Hostname.
>> Set the machine's hostname as your login followed by 42, according to the project guidelines.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/8.png">

> ### Domain Name.
>> Leave this field blank, as the project does not mention the need for a domain.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/9.png">

> ### Root Password.
>> Set a password for the root (system administrator) and remember or note it down.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/10.png">

> ### Repeat the process again to ensure that you didn't type it incorrectly.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/11.png">

> ### Create New User.
>> Create an additional user with your login for "daily use" (not root) and set a password for it.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/12.png">


> ### You need to enter the password for your new user.
>> I recommend use allways the same password to make it easier and simple.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/14.png"><br/>
> Repeat<br/>
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/15.png">

# Step 4: Time Zone Configuration

> ### Select the Time Zone.
>> Choose the region that corresponds to your country.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/16.png">

# Step 5: Disk Partitioning

> ### Choose Partitioning Method.
>> Select “Guided - use entire disk and set up encrypted LVM” to configure partitions with encrypted LVM.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/17.png">

> ### Select Disk.
>> Choose the disk you want to partition (usually the only one available).
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/18.png">

> ### Partitioning Option.
>> Choose `Separate /home partition`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/19.png">

> ### Write Changes.
>> Select “Yes” to confirm writing changes
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/20.png">

> ### LVM Configuration.
>> Click “Cancel” to prevent data deletion on the disk.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/21.png">

> ### Set Encryption Password.
>> Define a password for disk encryption and save it for future use.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/22.png">

> ### Allocate Space for the Logical Volume.
>> Enter “max” or the maximum value shown to allocate all the space.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/24.png">

# Step 6: Partitioning Finalization

> ### Finish and Confirm Changes.
>> Select `Finish partitioning and write changes to disk` and confirm with `Yes`.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/25.png">

> ### Further changes.
>> Choose `Yes` option to continue and confirm that you do not want to make further changes to the disk.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/26.png">

# Step 7: Package Configuration

> ### Additional packages.
>> We choose the `No` option because we do not need any additional packages.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/27.png">

> ### Configure Debian Mirror.
>> Select your country.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/28.png">

> ### Configure Debian Mirror.
>> Select the mirror `deb.debian.org`
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/29.png">

> ### Leave Proxy Option Blank.
>> Skip the proxy configuration by leaving it blank and clicking Continue.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/30.png">
<br/>

>> choose the `No` option.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/31.png">

> ### Package Options.
>> Deselect all package options using the space bar and click Continue.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/32.png">

# Step 8: GRUB Bootloader Installation

> ### Install GRUB.
>> Choose “Yes” to install GRUB on the hard drive.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/33.png">

> ### Select Boot Device.
>> Choose the `/dev/sda` device to install the bootloader.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/34.png">

# Step 9: Finalization

> ### Complete Installation.
>> After installing GRUB, select Continue to finish the process.
> <img width="600" src="https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/born2beroot/setupdevian/35.png">

# To continue follow the guide below:
### System Configuration ➔ [🇬🇧](https://github.com/AdaoG0n/42_Born2beroot/blob/main/systemsetup_en.md) [🇵🇹](https://github.com/AdaoG0n/42_Born2beroot/blob/main/systemsetup_pt.md)

![](https://github.com/AdaoG0n/AdaoG0n/blob/main/assests/animated%20gifs/madeby.gif)
