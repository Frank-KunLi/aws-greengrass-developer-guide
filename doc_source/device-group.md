# Create AWS IoT Devices in an AWS Greengrass Group<a name="device-group"></a>

1. In the AWS IoT console, choose **Greengrass**, choose **Groups**, and then choose your group to open its configuration page\. Next, choose **Devices** and then choose **Add your first Device**\.  
![\[Screenshot of the Devices page with the Add your first Device button highlighted.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-066.png)

   Choose **Create New Device**:  
![\[Screenshot of the Add a Device page with the Create New Device button highlighted.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-067.png)

   Register this device as **HelloWorld\_Publisher**, then choose **Next**:  
![\[Screenshot of Create a Registry entry for a device with the Name field set to HelloWorld_Publisher and the Next button highlighted.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-068.png)

   For **1\-Click**, choose **Use Defaults**:  
![\[Screenshot of Set up security with the Use Defaults button highlighted.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-069.png)

   Create a folder on your computer\.

   Download the certificates for your device into the folder, and then decompress them \(to decompress `tar.gz` files on Windows, see the **Windows** tab in step 2 of [Create and Package a Lambda Function](create-lambda.md)\)\.  
![\[Screenshot of the Download security credentials page with the Download these resources as a tar.gz button highlighted.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-070.png)

   Note the common GUID\-like filename component for the **HelloWorld\_Publisher** device \(in this example, `51d2737e90`\), this will be needed later\. Finally, choose **Finish**\.

1. By choosing **Add Device**, repeat step 1 to add another device to the group and name it **HelloWorld\_Subscriber**\. Download the certificates for your second device onto your computer as well, saving them in the same folder as the first set of certificates\. Choose **Finish**\. Again, note the common GUID\-like filename component for the **HelloWorld\_Subscriber** device\.

   You should now have two devices in your AWS Greengrass group:  
![\[Screenshot showing the HelloWorld_Publisher and HelloWorld_Subscriber devices.\]](http://docs.aws.amazon.com/greengrass/latest/developerguide/images/gg-get-started-071.png)

1. Download another [AWS IoT root certificate from Symantec](http://www.symantec.com/content/en/us/enterprise/verisign/roots/VeriSign-Class%203-Public-Primary-Certification-Authority-G5.pem) and save it as `root-ca-cert.pem` in the folder you just created\. For this module, this certificate and the certificates and keys for both devices should be in one folder on your computer \(not on the AWS Greengrass core device\)\.
**Note**  
If you're using a web browser on the Mac and you receive a This certificate is already installed as a certificate authority alert, you can open a Terminal window and run the following commands to download the certificate into the folder containing the HelloWorld\_Publisher and HelloWorld\_Subscriber device certificates/keys:  

   ```
   cd path-to-folder-containing-device-certificates
   curl -o ./root-ca-cert.pem http://www.symantec.com/content/en/us/enterprise/verisign/roots/VeriSign-Class%203-Public-Primary-Certification-Authority-G5.pem
   ```
Run `cat root-ca-cert.pem` to ensure that the file is not empty\. If so, check the URL and try the `curl` command again\.