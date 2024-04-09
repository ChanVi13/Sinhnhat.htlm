<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chúc Mừng Sinh Nhật Người Yêu</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }
        img {
            max-width: 100%;
            height: auto;
            margin-top: 20px;
        }
        #video-container {
            margin-top: 20px;
        }
        #video-frame {
            width: 640px;
            height: 360px;
        }
        #qr-code {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Chúc Mừng Sinh Nhật Người Yêu!</h1>
    <p>Những điều tốt đẹp nhất dành cho bạn!</p>

    <h2>Hình Ảnh Sinh Nhật</h2>
    <input type="file" id="image-upload" accept="image/*">
    <div id="image-preview"></div>

    <h2>Video Sinh Nhật</h2>
    <div id="video-container">
        <input type="text" id="video-link" placeholder="Nhập đường link video">
        <button onclick="changeVideo()">Thay đổi video</button>
        <br>
        <iframe id="video-frame" src="" frameborder="0" allowfullscreen></iframe>
    </div>

    <h2>Mã QR</h2>
    <div id="qr-code"></div>

    <script src="https://cdnjs.cloudflare.com/ajax/libs/qrious/4.0.2/qrious.min.js"></script>
    <script>
        document.getElementById('image-upload').addEventListener('change', function() {
            var file = this.files[0];
            var reader = new FileReader();
            reader.onload = function(e) {
                document.getElementById('image-preview').innerHTML = '<img src="' + e.target.result + '">';
            };
            reader.readAsDataURL(file);
        });

        function changeVideo() {
            var videoLink = document.getElementById("video-link").value;
            document.getElementById("video-frame").src = videoLink;
        }

        var qrCode = new QRious({
            element: document.getElementById('qr-code'),
            value: 'https://example.com',
            size: 200
        });
    </script>
</body>
</html>
