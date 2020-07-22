# Toast
 
Toast_Notify.ps1 is a simple Toast Notification script designed to be deployed as a package from MEMCM
Toast_Notify.ps1 will read an XML file on a file share so Toast Notifications can be changed "on the fly" without having to repackage. 
To create a custom XML, copy CustomMessage.xml and edit the text you want to display in the toast notification. Reference that file using one of the script parameters.

The following files should be present in the Script Directory when you create the package in MEMCM:-  
  
Toast_Notify.ps1
BadgeImage.jpg
HeroImage.jpg
CustomMessage.xml
  
.PARAMETER XMLScriptDirSource  
Specify the name of the XML file to read. The XML file must exist in the same directory as Toast_Notify.ps1. If no parameter is passed, it is assumed the XML file is called CustomMessage.xml.
  
.PARAMETER XMLOtherSource  
Specify the location of the Custom XML file used for the Toast when it is not in the MEMCM package
  
.EXAMPLE  
Toast_Notify.ps1 -XMLOtherSource "\\fileserverhome\xml\CustomMessage.xml"
  
.EXAMPLE  
Toast_Notify.ps1 -XMLSciptDirSource "PhoneSystemProblems.xml"
  
.EXAMPLE  
Toast_Notify.ps1
  
**Known Issues**  
Currently, the images in the XML can only be read from the local files system. This is not an issue if we are deploying the package from MEMCM. Further development will see the ability to convert images to Base64 or host them on a web server
