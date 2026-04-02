<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>PDF Viewer</title>

  <!-- Adobe PDF Embed API -->
  <script src="https://acrobatservices.adobe.com/view-sdk/viewer.js"></script>

  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: #f5f5f5;
    }

    header {
      padding: 16px;
      background: #222;
      color: white;
      text-align: center;
      font-size: 18px;
    }

    #adobe-dc-view {
      height: calc(100vh - 60px);
      width: 100%;
    }
  </style>
</head>
<body>

<header>
  PDF Viewer (Adobe Embed API)
</header>

<div id="adobe-dc-view"></div>

<script>
document.addEventListener("adobe_dc_view_sdk.ready", function () {
  const adobeDCView = new AdobeDC.View({
    clientId: "YOUR_ADOBE_CLIENT_ID",
    divId: "adobe-dc-view"
  });

  adobeDCView.previewFile({
    content: {
      location: {
        url: window.location.origin + "/AbsenceRequest.pdf"
      }
    },
    metaData: {
      fileName: "AbsenceRequest.pdf"
    }
  }, {
    embedMode: "SIZED_CONTAINER",
    showDownloadPDF: true,
    showPrintPDF: true
  });
});
</script>

</body>
</html>
