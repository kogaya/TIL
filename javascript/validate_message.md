HTML5でのフォームバリデーションのエラーメッセージを任意のものに変更する

[[参考]](https://girliemac.com/blog/2012/12/01/html5-form-validation-jp/)　[[参考２]](https://qiita.com/leedohyung-dba/items/b762e21018edc4d0387c)

```html
<html>

<body>
    <form>
        <input id="username" type="text" required>
        <input id="password" type="text" required>
        <select id="plan" required>
            <option value="">プランを選択してください</option>
            <option value="1">プランA</option>
            <option value="2">プランB</option>
            <option value="3">プランC</option>
        </select>
        <input type="submit">
    </form>
</body>

<script>
    var targets = [
        { id: "username", message: "ユーザ名を入力してください" },
        { id: "password", message: "パスワードを入力してください" },
        { id: "plan", message: "プランを選択してください" },
    ]

    function setRequiredMessage(id, message) {
        var target = document.getElementById(id)
        target.addEventListener('invalid', function (e) {
            if (e.target.validity.valueMissing) {
                e.target.setCustomValidity(message);
            }
            e.target.addEventListener('input', function (e) {
                e.target.setCustomValidity("");
            }, false)
        }, false)
    }

    targets.forEach(function (val) {
        setRequiredMessage(val.id, val.message)
    })

</script>

</html>
```

チェックボックスにチェックが入っていたら入力必須というようなケースは、チェックボックスにチェックが入っていないとき、`input`を`disable`にすることで対処可能。

`disable`のときはバリデーションの対象にならない
