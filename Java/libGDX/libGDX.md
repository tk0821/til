# libGDX

Javaのクロスプラットフォーム対応ゲーム開発用フレームワーク。

Windows, Linux, macOS, Android, iOS, ブラウザに対応。

## プロジェクト生成

libGDXにはプロジェクトセットアップツールがあり、それを使うことで簡単にプロジェクトを生成できる。

## ディレクトリ

`core/src` にゲームのコードを入れる。

各プラットフォームのディレクトリはそのプラットフォームでのランチャーのコードが含まれる。

## ランチャー(desctop)
```Java

Lwjgl3ApplicationConfiguration config = new Lwjgl3ApplicationConfiguration();

/* config設定
   ...
*/

// ゲームのエントリーポイントになるクラスを渡してアプリケーション起動
new Lwjgl3Application(new applicationlistener(), config);

```

## ApplicationAdapter

applicationlistenerを簡単に実装できるクラス。

必要なメソッドだけをオーバーライドする


``` Java

public Sample extends ApplicationAdapter {

  void create();  //　アプリケーション作成時に呼ばれる　初期化処理
  void dispose();　//　アプリケーション破棄時に呼ばれる　メモリ開放など
  void pause();  //　アプリケーションが一時停止しているときに呼ばれる
  void render();  //　描画が必要な時に呼ばれる
  void resize();  //　サイズが変更されたときに呼ばれる
  void resume();  //　一時停止から再開するときによばれる

}
```
### Screen

画面遷移を行う場合は、Gameクラス、Screenクラスを使う。

Gameクラスがエントリポイントとなり、setScreenメソッドで画面遷移を行う

``` Java
public Sample extends Screen {

  void dispose();　//　アプリケーション破棄時に呼ばれる　メモリ開放など
  void pause();  //　アプリケーションが一時停止しているときに呼ばれる
  void render();  //　描画が必要な時に呼ばれる
  void resize();  //　サイズが変更されたときに呼ばれる
  void resume();  //　一時停止から再開するときによばれる
  void hide();  //　表示している画面ではなくなったときに呼ばれる
  void show();  //　表示する画面になるときに呼ばれる
}
```
createはない。

## InputAdapter

InputProcessorを簡単に実装できるクラス。

キー入力や、マウス操作時に呼び出される動作を実装できる。

Gdx.input.setInputProcessorメソッドに渡すことで呼び出されるようになる。


