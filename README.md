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

How to use
-------------
Add the azureBlob service as a dependacy to your controller like so:
```javascript
angular.module('myapp')
  .controller('MainCtrl', function ($scope, azureBlob) {
  ...
})
```

This will expose the following method

* azureBlob.upload(config)

The config object has the following properties

```javascript
{
  baseUrl: // baseUrl for blob file uri (i.e. http://<accountName>.blob.core.windows.net/<container>/<blobname>),
  sasToken: // Shared access signature querystring key/value prefixed with ?,
  file: // File object using the HTML5 File API,
  progress: // progress callback function,
  complete: // complete callback function,
  error: // error callback function,
}
```


CORS
-------------

Cross Origin Resource Sharing (CORS) must be enabled on the azure blob storage account. The following articles can assist with this...

[Windows Azure Storage Introducing CORS](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/02/03/windows-azure-storage-introducing-cors.aspx)
[Windows Azure Storage and CORS](http://www.contentmaster.com/azure/windows-azure-storage-cors/)