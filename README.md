# png2jpg-for-a1111-and-NAI
[日本語](#日本語) | [English](#en)

# 日本語

# 説明
## 1. Automatic1111生成画像の変換について
- Automatic1111に取り込むことが可能なメタデータを維持したままPNG(.png)をJPEG(.jpg)に変換します。  
- 元画像のメタデータ（PNG Info）はJPEG画像のExifコメントに格納されます。  
- JPEG画像は元画像同様にAutomatic1111のPNG Infoから情報を読み込ませて利用することが可能です。

## 2. NovelAI生成画像の変換について
- PNG画像に格納されているメタデータをJPEGに格納することができます。  
- 元画像のメタデータはJPEG画像のExifコメントに格納されます。  
- NovelAIやAutomatic1111に情報を読み込ませることはできませんが、Automatic1111のPNG InfoやWindowsのエクスプローラ等で情報を参照することが可能です。  
- [jpg2png-for-NAI](https://github.com/Takenoko3333/jpg2png-for-NAI)を使用することでNovelAIやAutomatic1111で取り込み可能なPNG画像に再変換することができます。

## 3. 日付情報について
元画像の日付情報を変換後の画像に引き継ぎます。  
- Windows: 更新日時, 作成日時  
- Mac, Linux: 更新日時
<br><br>
# 前提
Python3環境
<br><br>
# 準備
以下のライブラリを使用するため、入っていない場合はインストールします。
- PIL  
~~~
pip install pillow
~~~

- piexif  
~~~
pip install piexif
~~~

Windowsのみ  
- pywin32  
~~~
pip install pywin32
~~~
<br>

# 使い方
1. inputsフォルダに変換したいPNG画像を入れます。  
2. png2jpg.batをダブルクリックします。コマンドラインが起動します。  
3. outputsフォルダにJPEG画像が保存されます。コマンドラインが閉じます。
<br><br>
# 設定変更等
- JPEG品質の初期設定は80です。変更したい場合はpng2jpg.py内のJPEG_QUALITYを編集してください。  
- 処理完了後にコマンドラインを閉じないようにしたい場合はpng2jpg.bat内の@REM pauseのコメントアウトを外してください。
<br><br>
# 変更履歴

## [1.1.1] - 2023-12-17
### 変更
- README.md修正。

## [1.1.0] - 2023-12-12
### 追加
- 日付情報の維持に対応。Windowsの場合は更新日時と作成日時、Mac, Linuxの場合は更新日時が変換後の画像に引き継がれます。

## [1.0.0] - 2023-12-10
### 修正
- Automatic1111生成画像を変換した場合にプロンプト冒頭に"parameters: "が混入していた問題を修正。
- 既に変換した画像は別途配布の[jpg2jpg-bugfix-metadata](https://github.com/Takenoko3333/jpg2jpg-bugfix-metadata)で一括修正できます。 
- GitHubで公開 

## 2023-12-08
### 追加
- Megaにてpng2jpg改として初版リリース。
<br><br>
# ライセンス
Copyright © 2023 Takenoko  
Released under the [MIT](https://opensource.org/licenses/mit-license.php) license.
<br><br>
# en

# Description
## 1. Conversion of Automatic1111 generated images
- Converts PNG (.png) to JPEG (.jpg) while maintaining metadata that can be imported into Automatic1111.  
- The metadata (PNG Info) of the original image is stored in the Exif comment of the JPEG image.  
- The JPEG image can be used by reading the information from the PNG Info in Automatic1111 as well as the original image.

## 2. Conversion of NovelAI generated images
- Metadata stored in the PNG image can be stored in the JPEG image.  
- The metadata of the original image is stored in the Exif comment of the JPEG image.  
- It is not possible to load the information into NovelAI or Automatic1111, but it is possible to refer to the information using PNG Info in Automatic1111, Windows Explorer, etc.  
- You can use [jpg2png-for-NAI](https://github.com/Takenoko3333/jpg2png-for-NAI) to reconvert the information to a PNG image that can be imported by NovelAI or Automatic1111.

## 3. About date information
The date information of the original image will be transferred to the converted image.  
- Windows: Modified date, Created date  
- Mac, Linux: Modified date
<br><br>
# Assumptions
Python3 environment
<br><br>
# Preparation
The following libraries are used, so install them if they are not included.
- PIL  
~~~
pip install pillow
~~~

- piexif  
~~~
pip install piexif
~~~

Windows only  
- pywin32  
~~~
pip install pywin32
~~~
<br>

# How to use
1. put the PNG images you want to convert in the inputs folder.
2. Double-click on png2jpg.bat. A command line will be launched.
3. JPEG images will be saved in the outputs folder. The command line will close.
<br><br>
# Change settings, etc.
- The default JPEG quality setting is 80. If you want to change it, edit JPEG_QUALITY in png2jpg.py.  
- If you do not want to close the command line after processing is complete, uncomment @REM pause in png2jpg.bat.
<br><br>
# Change log

## [1.1.1] - 2023-12-16
### Changed
- README.md fix.

## [1.1.0] - 2023-12-12
### Added
- Added support for maintaining date information: modified and created date/time for Windows, modified date/time for Mac and Linux will be inherited by the converted image.

## [1.0.0] - 2023-12-10
### Fixed
- Fixed a problem that "parameters:" was mixed in the beginning of the prompt when converting Automatic1111-generated images.
- Already converted images can be fixed with [jpg2jpg-bugfix-metadata](https://github.com/Takenoko3333/jpg2jpg-bugfix-metadata) distributed separately. 
- Published on GitHub. 

## 2023-12-08
### Added
- First released on Mega as png2jpg modification.
<br><br>
# License
Copyright © 2023 Takenoko  
Released under the [MIT](https://opensource.org/licenses/mit-license.php) license.


