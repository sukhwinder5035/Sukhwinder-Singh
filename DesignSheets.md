<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Download Files</title>
</head>
<body>
    <h1>Download Files (JM'24_Design of Steel Structures)</h1>

    <button onclick="downloadFile('https://raw.githubusercontent.com/sukhwinder5035/Sukhwinder-Singh/main/Files/Isolated Footing.xlsx')">Download .xlxs (Isolated Footing.xlsx)</button>
    
    <script>
        function downloadFile(fileUrl) {
            fetch(fileUrl)
                .then(response => response.blob())
                .then(blob => {
                    const link = document.createElement('a');
                    link.href = window.URL.createObjectURL(blob);
                    link.download = fileUrl.substring(fileUrl.lastIndexOf('/') + 1);
                    document.body.appendChild(link);
                    link.click();
                    document.body.removeChild(link);
                })
                .catch(error => console.error('Error downloading file:', error));
        }
    </script>
</body>
</html>
