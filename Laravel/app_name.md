`.env`ファイルの`APP_NAME`に日本語でシステムの名前を記入したところエラー

アプリ名が空になっていた

どうやら`.env`ファイルは日本語に対応していないようなので

英名にするか、`.env`の値を参照している場所に直接記述するかで対応するしかない模様