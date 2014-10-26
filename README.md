angular-azure-blob-upload
=========================

AngularJS service for uploading to azure blob storage.

Provides for the ability to upload to azure blob storage. It uploads it in chunks avoiding memory constraints of large files as a BlockBlob. The upload uses a Shared Access Signature (SAS) to secure the file upload.

Required dependencies
-----------------------
* [AngularJS] (http://www.angularjs.com) 

Add the Azure Blob Upload to your index.html file 
```HTML
<script src='/client/js/lib/azure-blob-upload.js'></script>
```

After downloading the `azure-blob-upload.js` to your AngularJS project then

Add `'azureBlobUpload'` to your main angular.module like so
```javascript
angular.module('myapp', ['myApp.controllers', 'myApp.services', 'azureBlobUpload']);
````