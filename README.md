# Style-Transfer-colab

ニューラルネットワークを使ったスタイル変換をGoogle Colaboratory上で実行する。  

現状は[Gatys et al. 2016](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)のNeural Style Transferのみ。

ここに画像を入れたい。
  ![dancing](https://user-images.githubusercontent.com/38127823/78241990-3fe92700-751c-11ea-868c-3c4ed7d6e0a0.jpg)![picasso-dancing](https://user-images.githubusercontent.com/38127823/78242047-52fbf700-751c-11ea-9537-dccdb97d8fc7.jpg)


## cloneの仕方

自分のGoogleドライブのマイドライブにterminal.ipynbを作り、以下を実行する。

```Python
from google.colab import drive
drive.mount('/content/drive')
%cd drive/My\ Drive
```
まずドライブを[マウント](https://qiita.com/asakuraTsukazaki/items/e7eb1f0c43be1e0231c6)する。　　

次に、このリポジトリをgit cloneする。
```
!git clone https://<自分のGitアカウント>:<Gitパスワード>@github.com/Kanazawanaoaki/Style-Transfer-colab.git
```
マイドライブにcloneされて、ディレクトリが出来ているはず。 以降pullやpushをする時はこのノートブックから行う。

## 使い方
- スタイル変換に使いたい画像をimagesフォルダの中に入れておく。  
- noteboooksフォルダの中にあるNeural-Style-Transfer.ipynbを開く。  

- notebookの #画像のpathを指定 の部分を使いたい画像の名前に変更する。拡張子が.jpgでない場合はそこも変更する。  
- 入力画像としてコンテンツ画像を使う場合はwhite_flagをFalseに、ホワイトノイズを使う時はTrueにする。  

- パラメータを変更する場合は、notebookの下の方にある #スタイル変換を実行 の部分の値を変更する。  
- ノートブックを実行するとスタイル変換が実行されて、outputsフォルダに生成された画像が保存される。  

## フォルダの説明
- images：スタイル変換に使いたい画像を入れておくフォルダ  
- notebooks：.ipynb形式のノートブックが入っているフォルダ 
- outputs：生成画像が保存されるフォルダ

notebooksの中には、自分で用意した画像にスタイル変換を実行できるNeural-Style-Transfer.ipynbと、[Pytorchの公式チュートリアル](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html)をほぼそのまま書いてあるneural-transfer-tutorial.ipynbがある。  

## 今後
今回の[Gatys et al. 2016](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)をベースとした改良版のスタイル変換手法や、[pix2pix](https://arxiv.org/abs/1611.07004)や[CycleGAN](https://arxiv.org/abs/1703.10593)などのGANを使ったスタイル変換も実装していきたい。
