# training
<!DOCTYPE html>
<html lang="ja">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css">
    <title>筋トレ</title>
</head>

<body>
    <div class="columns is-vcentered is-centered" style="height: 100vh;">
        <div class="box column is-2 has-background-white-bis">
            <button class="button is-white is-size-1 is-large" id="btn" style="  left: 50%;
                                transform: translateX(-50%);">

            </button>
        </div>
    </div>
</body>
<script>
    let btn = document.getElementById("btn");
    let date = new Date();
    let number;
    if (localStorage.getItem("count") != null) {
        number = localStorage.getItem("count");
    } else {
        number = 10;
    }
    btn.innerText = number;
    if (date.getDate() != localStorage.getItem("date")) {
        btn.disabled = false;
    }

    btn.onclick = () => {
        number++;
        btn.disabled = true;
        localStorage.setItem("count", number);
        localStorage.setItem("date", date.getDate());
        btn.innerText = number;
    }

</script>

</html>
