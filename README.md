<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>liens de site Web</title>
    <style>
        /* الأسلوب الأساسي */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            line-height: 1.6;
            position: relative;
            transition: background-color 0.5s, color 0.5s; /* إضافة انتقال سلس */
        }

        /* الأوضاع */
        body.light-mode {
            background-color: #f4f4f9;
            color: #333;
        }

        body.dark-mode {
            background-color: #121212;
            color: #ffffff;
        }

        /* عرض الساعة والتاريخ في الأعلى */
        .header {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 10px 20px;
            transition: color 0.5s;
        }

        .clock, .date {
            font-size: 24px;
            font-weight: bold;
            margin: 5px 0;
        }

        /* نص GÉNIE ÉLECTRIQUE */
        .footer-text {
            position: absolute;
            bottom: 10px;
            left: 10px;
            font-size: 14px;
            font-weight: bold;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
            transition: color 0.5s;
        }

        /* تصميم container */
        .container {
            max-width: 600px;
            margin: 20px auto 0;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            transition: background-color 0.5s, box-shadow 0.5s;
        }

        body.light-mode .container {
            background: rgba(255, 255, 255, 0.9);
        }

        body.dark-mode .container {
            background: rgba(0, 0, 0, 0.8);
            box-shadow: 0 4px 10px rgba(255, 255, 255, 0.1);
        }

        h1 {
            text-align: center;
        }

        .link-item a {
            display: inline-block;
            padding: 10px 20px;
            color: #ffffff;
            text-decoration: none;
            border-radius: 5px;
            transition: background-color 0.5s;
        }

        .myway {
            background-color: #16CDE3;
        }

        .ofppt-langue {
            background-color: #8D9492;
        }

        .scholarvox {
            background-color: #1D9D17;
        }

        .ofppt {
            background-color: #1C45E4;
        }

        /* زر تبديل الوضع (دائرة) */
        .toggle-button {
            position: absolute;
            top: 10px;
            right: 10px;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 50%; /* دائرة */
            transition: background-color 0.5s, color 0.5s;
        }

        body.light-mode .toggle-button {
            background-color: #1C45E4;
            color: #fff;
        }

        body.dark-mode .toggle-button {
            background-color: #ffffff;
            color: #1C45E4;
        }

        /* تمركز الروابط في الوسط */
        .link-item {
            text-align: center;
            margin-bottom: 15px;
        }

        /* استهداف الهواتف */
        @media (max-width: 768px) {
            body {
                padding: 10px;
            }

            .header {
                padding: 5px 10px;
            }

            .clock, .date {
                font-size: 18px;
            }

            .container {
                max-width: 100%;
                padding: 15px;
            }

            .link-item a {
                font-size: 14px;
                padding: 8px 16px;
            }

            .toggle-button {
                width: 35px;
                height: 35px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body class="light-mode">
    <!-- زر تبديل الوضع (دائرة) -->
    <button id="toggleMode" class="toggle-button">☀️</button>

    <!-- عرض الساعة والتاريخ في الأعلى -->
    <div class="header">
        <div id="clock" class="clock"></div>
        <div id="date" class="date"></div>
    </div>

    <div class="container">
        <h1>liens de site Web</h1>
        <div class="link-item">
            <a href="https://www.myway.ac.ma/fr" target="_blank" class="myway">MY WAY</a>
        </div>
        <div class="link-item">
            <a href="https://altissia.org/fr/ofppt-langues" target="_blank" class="ofppt-langue">OFPPT LANGUE</a>
        </div>
        <div class="link-item">
            <a href="https://www.scholarvox.com/" target="_blank" class="scholarvox">SCHOLARVOX</a>
        </div>
        <div class="link-item">
            <a href="https://www.ofppt.ma/" target="_blank" class="ofppt">OFPPT</a>
        </div>
    </div>

    <!-- النص في الأسفل على اليسار -->
    <div class="footer-text">GÉNIE ÉLECTRIQUE 103</div>

    <script>
        // وظيفة لإظهار الوقت والتاريخ
        function updateDateTime() {
            const now = new Date();
            const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
            document.getElementById('clock').textContent = now.toLocaleTimeString();
            document.getElementById('date').textContent = now.toLocaleDateString('fr-FR', options);
        }

        // تحديث الوقت والتاريخ كل ثانية
        setInterval(updateDateTime, 1000);

        // بدء العرض عند تحميل الصفحة
        updateDateTime();

        // تبديل الوضع بين Dark mode و Light mode
        const toggleButton = document.getElementById('toggleMode');
        const body = document.body;

        toggleButton.addEventListener('click', () => {
            if (body.classList.contains('light-mode')) {
                body.classList.remove('light-mode');
                body.classList.add('dark-mode');
                toggleButton.textContent = '🌙'; // رمز للوضع الليلي
            } else {
                body.classList.remove('dark-mode');
                body.classList.add('light-mode');
                toggleButton.textContent = '☀️'; // رمز للوضع النهاري
            }
        });
    </script>
</body>
</html>
