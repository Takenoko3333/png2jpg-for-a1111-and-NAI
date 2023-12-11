# png2jpg-for-a1111-and-NAI

## リリースノート
* 2023/12/08 初版リリース。  
* 2023/12/10 Automatic1111生成画像を変換した場合にプロンプト冒頭に"parameters: "が混入していた問題を修正。既に変換した画像は別途配布の[jpg2jpg-bugfix-metadata](https://github.com/Takenoko3333/jpg2jpg-bugfix-metadata)で一括修正できます。  
* 2023/12/11 日付情報の維持に対応。Windowsの場合は更新日時と作成日時、Mac, Linuxの場合は更新日時が変換後の画像に引き継がれます。

## 説明
### 1. Automatic1111生成画像の変換について
Automatic1111に取り込むことが可能なメタデータを維持したままPNG(.png)をJPEG(.jpg)に変換します。  
元画像のメタデータ（PNG Info）はJPEG画像のExifコメントに格納されます。  
JPEG画像は元画像同様にAutomatic1111のPNG Infoから情報を読み込ませて利用することが可能です。

### 2. NovelAI生成画像の変換について
PNG画像に格納されているメタデータをJPEGに格納することができます。  
元画像のメタデータはJPEG画像のExifコメントに格納されます。  
NovelAIやAutomatic1111に情報を読み込ませることはできませんが、Automatic1111のPNG InfoやWindowsのエクスプローラ等で情報を参照することが可能です。  
[jpg2png-for-NAI](https://github.com/Takenoko3333/jpg2png-for-NAI)を使用することでNovelAIやAutomatic1111で取り込み可能なPNG画像に再変換することができます。

## 前提
Python環境

## 準備
以下のライブラリを使用するため、入っていない場合はインストールします。
* PIL  
pip install pillow

* piexif  
pip install piexif

Windowsの場合  
* pywin32  
pip install pywin32

## 使い方
1. inputsフォルダに変換したいPNG画像を入れます。  
2. png2jpg.batをダブルクリックします。  
3. outputsフォルダにJPEG画像が保存されます。

## 設定変更等
JPEG品質の初期設定は80です。変更したい場合はpng2jpg.py内のJPEG_QUALITYを編集してください。  
処理完了後にコマンドラインを閉じないようにしたい場合はpng2jpg.bat内の@REM pauseのコメントアウトを外してください。
