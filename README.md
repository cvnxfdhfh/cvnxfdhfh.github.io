<!DOCTYPE html>
<html lang="he">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>חיפוש מידע על חסידויות</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            direction: rtl;
            text-align: center;
            background-color: #f7f7f7;
            color: #333;
        }
        h1 {
            color: #4CAF50;
        }
        input[type="text"] {
            width: 80%;
            padding: 10px;
            font-size: 1em;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            font-size: 1em;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .result {
            margin-top: 20px;
            font-size: 1.1em;
            color: #555;
        }
    </style>
</head>
<body>
    <h1>חיפוש מידע על חסידויות</h1>
    <p>הכנס את שם החסידות שברצונך למצוא מידע עליה:</p>
    <input type="text" id="searchInput" placeholder="הקלד שם חסידות...">
    <button onclick="search()">חפש</button>

    <div class="result" id="result"></div>

    <script>
        const data = {
            "חב\"ד": "חסידות חב\"ד נוסדה על ידי רבי שניאור זלמן מליאדי והתרכזה במזרח אירופה. כיום, חב\"ד פעילה בכל העולם ומפורסמת בשל שליחיה הרבים.",
            "ברסלב": "חסידות ברסלב נוסדה על ידי רבי נחמן מברסלב ומתאפיינת באמונה בשמחה ובחסד. החסידות צמחה בעיקר באוקראינה ומרכזת חסידים רבים.",
            "בעלז": "חסידות בעלז נוסדה בגליציה על ידי רבי שלום רוקח והיא כיום אחת מהחסידויות הגדולות בעולם, עם ריכוז גדול בישראל ובארצות הברית.",
            "גור": "חסידות גור היא מהחסידויות הגדולות בישראל, עם מספר חסידים רב. היא נוסדה בפולין ומונהגת כיום בידי האדמו\"ר מגור."
        };

        function search() {
            const query = document.getElementById("searchInput").value.trim();
            const resultDiv = document.getElementById("result");
            
            if (query in data) {
                resultDiv.innerHTML = `<strong>מידע על ${query}:</strong><br>${data[query]}`;
            } else if (query) {
                resultDiv.innerHTML = `מצטערים, לא נמצא מידע על ${query}.`;
            } else {
                resultDiv.innerHTML = "";
            }
        }
    </script>
</body>
</html>
