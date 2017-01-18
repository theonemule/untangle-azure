Build an Untangle VM in VirtualBox
====

**You can skip this section and just download the image from Google Drive that is already prepared.**

This process takes about 30-45 minutes to complete depending on your setup. To create a VM on VirtualBox, you'll need to have [VirtualBox](https://www.virtualbox.org/wiki/Downloads) installed on your computer and a [ISO of Untangle 64-bit downloaded](https://www.untangle.com/get-untangle/) from Untangle. 


####Configure VirtualBox

1. Launch VirtualBox and click "New".

1. On the first screen on the wizard...

	* Give the VM a name. It can be anything you want
	* Select **Linux** for **Type**.
	* Debian **64-bit** for the **Version**.

1. For **Memory Size** screen, select at least **4 GB** of RAM.

1. For **Hard Disk** screen,  select **Create a virtual disk now**

1. For **Hard Disk File Type** screen, select **VHD (Virtual Hard Disk)**. This is important because this is the format that Azure uses for its VM's.

1. For **Storage on Physical Disk** screen, select **Dynamically Allocated**.

1. For **File Location and Size** screen, set the name of the disk and the the size to at least **32 GB**.  After this is done, VirtualBox will create the V. Don't start it yet.

1. Click the **Settings** icon to edit the settongs.

1. Select **System** -> then **Processor**

1. Set the processor count to **2**

1. Check the box next to **Enable PAE/NX**

1. Select **Audio** and uncheck **Enable Audio**

1. Select **Network** -> **Adapter 2**, and check the box next to **Enable Network Adapter**, then set Attached to **Host-only Adapter**.

1. Select **USB**, then uncheck the box next to Enable USB Controller

1. Select **Storage**, then click **Empty** under **Controller IDE**.

1. Next to **Optical Drive**, there is a CD disk icon. Click the disk icon and then select **Choose Virtual Optical Disk File...**. Find the Untangle ISO you downloaded from Untangle, then click OK.

1. Once these settings are set, start the VM and install Untangle as normal.

####Configure Untangle

1. After Untangle boots for the first time, the setup wizard will run.

1. Pick your **Language**, then click **continue**. Click passed the welcome screen.

1. Under password, set the **password**, repeat it, then enter your admin email address for **Admin Email**, then **Select a Timezone**.

1. Take the defaults on the **Identify Network Cards** page.

1. Take the defaults on the **Configure the Internet Connection** page.

1. On the **Internal Network**, set the **Internal Address** to **10.0.2.5**. Uncheck the box next to **Enable DHCP Server**.

1. Take the defaults on **Automatic Upgrades**.

1. Click Finish to **Finish** the setup.

1. When the account registration screen comes up, **don't login**. Simply close it.

1. Go to **Config** -> **Network** -> **Advanced** -> **Filter Rules** and check the boxes next to Allow SSH to **Enable SSH Access**, then click **OK**. It will prompt you about enabling SSH. Click **Yes**. SSH is necessary on Azure to get connected to the Untangle Firewall to configure it. If you don't like using port 22, you can change the port to something else on Untangle to make it more obscure.

1. Once the configuration redirects back to the **Account Registration** screen, close the browser and **Shutdown** Untangle. The setup if the virtual hard drive is complete and ready to be uploaded to Azure.
