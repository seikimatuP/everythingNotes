# Laravel_注意事項  
  
個人的なお遊びで何となく注意することを羅列
  
# 開発環境  
・MacOS Catalina  
・Laravel ver5.5  
・MySQL 8.0.22  
  
# 注意事項一覧  
・DBの起動してる？ -> してなきゃエラー  

・php artisan serveしてない?

・Laravelのバージョン違い(とりあえず、自分が遭遇したのだけ記載)  

    1：@csrf  
        CSRF(クロスサイトリクエストフォージェリ)チェックするやつ  
        トークンを自動生成して、認証済みユーザがリクエストしているか確認してくれるらしい  
        https://readouble.com/laravel/5.5/ja/csrf.html

    2：@method('DELETE')
        擬似フォームメソッドっていうらしい。htmlフォームはupdate・put・patchリクエストを作成できないからこいつで作ってあげる感じ。  
        patchはupdateの概念に近いらしい。putはpostに近いけど厳密には違うらしい
        https://readouble.com/laravel/5.6/ja/controllers.html  
        https://developer.mozilla.org/ja/docs/Web/HTTP/Methods/PATCH
        
    3：Route::resource('todos','TodoController');
        ルーティング一括で記載できるみたい。  
        リソースに対する様々なアクションを処理する複数のルートがこの定義により生成されるとのこと。
        今までワイが知ってた書き方：Route::get('/todos', 'TodoController@index');

        以下のコマンドでコントローラを生成した場合、表のようなルートの定義が生成される
        php artisan make:controller PhotoController --resource





