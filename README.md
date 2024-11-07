<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Giải Phương Trình Bậc 2</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f9f9f9;
        }

        input {
            margin: 5px 0;
            padding: 5px;
            width: 100px;
        }

        #ketqua {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <h1>Giải Phương Trình Bậc 2</h1>
    <label for="a">Nhập A:</label>
    <input type="number" id="a" required><br>

    <label for="b">Nhập B:</label>
    <input type="number" id="b" required><br>

    <label for="c">Nhập C:</label>
    <input type="number" id="c" required><br>

    <input type="button" value="Giải Phương Trình" onclick="giaiPhuongTrinh()">

    <div id="ketqua"></div>

    <script>
        function giaiPhuongTrinh() {
            const a = parseFloat(document.getElementById("a").value);
            const b = parseFloat(document.getElementById("b").value);
            const c = parseFloat(document.getElementById("c").value);
            const ketqua = document.getElementById("ketqua");

            if (a === 0) {
                ketqua.innerHTML = "A không được bằng 0. Vui lòng nhập A khác 0.";
                return;
            }

            const delta = b * b - 4 * a * c;

            if (delta > 0) {
                const x1 = (-b + Math.sqrt(delta)) / (2 * a);
                const x2 = (-b - Math.sqrt(delta)) / (2 * a);
                ketqua.innerHTML = `Phương trình có 2 nghiệm phân biệt: x1 = ${x1}, x2 = ${x2}`;
            } else if (delta === 0) {
                const x = -b / (2 * a);
                ketqua.innerHTML = `Phương trình có nghiệm kép: x = ${x}`;
            } else {
                ketqua.innerHTML = "Phương trình vô nghiệm.";
            }
        }
    </script>

</body>
</html>
