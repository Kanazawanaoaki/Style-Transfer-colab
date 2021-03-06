# Style-Transfer-colab

ニューラルネットワークを使ったスタイル変換をGoogle Colaboratory上で実行する。  

現状は[Gatys et al. 2016](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)のNeural Style Transferのみ。やったことなどを簡単に[ブログ](https://kanazawanaoaki.hatenablog.com/entry/2020/04/02/203255)に書いてあります。

|コンテンツ画像|生成画像|スタイル画像|
|---|---|---|
|![dancing](https://user-images.githubusercontent.com/38127823/78241990-3fe92700-751c-11ea-868c-3c4ed7d6e0a0.jpg)|![picasso-dancing](https://user-images.githubusercontent.com/38127823/78242047-52fbf700-751c-11ea-9537-dccdb97d8fc7.jpg)|![picasso](https://user-images.githubusercontent.com/38127823/78242020-48d9f880-751c-11ea-9ac8-8a3244aef427.jpg)|

|コンテンツ画像|
|---|
|![Tuebingen_Neckarfront](https://user-images.githubusercontent.com/38127823/78241659-b8031d00-751b-11ea-9bd6-0327e898219b.jpg)|  

|生成画像|スタイル画像|
|---|---|
|![Tuebingen_Neckarfront-Composition_VII-wn-500epoch-sw200000-cw1](https://user-images.githubusercontent.com/38127823/78315014-b9bdf680-7596-11ea-9798-bf50a6f82068.jpg)|![Composition_VII](https://user-images.githubusercontent.com/38127823/78315050-d3f7d480-7596-11ea-9626-09d85677e623.jpg)|
|![Tuebingen_Neckarfront-Femme_nue_assise-wn-500epoch-sw200000-cw1](https://user-images.githubusercontent.com/38127823/78315017-bc205080-7596-11ea-9da6-ea37fcb05c55.jpg)|![Femme_nue_assise](https://user-images.githubusercontent.com/38127823/78315065-db1ee280-7596-11ea-9e8e-4df608584355.jpg)|
|![Tuebingen_Neckarfront-The_Shipwreck_of_the_Minotaur-500epoch-sw2000000-cw1](https://user-images.githubusercontent.com/38127823/78315018-bcb8e700-7596-11ea-9b95-1e33f00b5953.jpg)|![The_Shipwreck_of_the_Minotaur](https://user-images.githubusercontent.com/38127823/78315073-e3771d80-7596-11ea-8a90-f36fd9644494.jpg)|
|![Tuebingen_Neckarfront-The_Starry_Night-wn-500epoch-sw200000-cw1](https://user-images.githubusercontent.com/38127823/78315020-bcb8e700-7596-11ea-9dc2-31e2d638d82b.jpg)|![The_Starry_Night](https://user-images.githubusercontent.com/38127823/78315083-e7a33b00-7596-11ea-984d-7dd58d77f77a.jpg)|




## googleドライブへのcloneの仕方

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
<img width="748" alt="スクリーンショット 2020-04-02 19 36 39" src="https://user-images.githubusercontent.com/38127823/78242868-bdf9fd80-751d-11ea-8fbc-a545a85d3bb1.png">  

- notebookの #画像のpathを指定 の部分を使いたい画像の名前に変更する。拡張子が.jpgでない場合はそこも変更する。  
- 入力画像としてコンテンツ画像を使う場合はwhite_flagをFalseに、ホワイトノイズを使う時はTrueにする。  
<img width="251" alt="スクリーンショット 2020-04-02 19 39 33" src="https://user-images.githubusercontent.com/38127823/78242887-c6523880-751d-11ea-858d-677eccb2ed47.png">  

- パラメータを変更する場合は、notebookの下の方にある #スタイル変換を実行 の部分の値を変更する。   
- ノートブックを実行するとスタイル変換が実行されて、outputsフォルダに生成された画像が保存される。  



## フォルダの説明
- images：スタイル変換に使いたい画像を入れておくフォルダ  
- notebooks：.ipynb形式のノートブックが入っているフォルダ 
- outputs：生成画像が保存されるフォルダ

notebooksの中には、自分で用意した画像にスタイル変換を実行できるNeural-Style-Transfer.ipynbと、[Pytorchの公式チュートリアル](https://pytorch.org/tutorials/advanced/neural_style_tutorial.html)をほぼそのまま書いてあるneural-transfer-tutorial.ipynbがある。  



## 今後
今回の[Gatys et al. 2016](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)をベースとした改良版のスタイル変換手法や、[pix2pix](https://arxiv.org/abs/1611.07004)や[CycleGAN](https://arxiv.org/abs/1703.10593)などのGANを使ったスタイル変換も実装していきたい。
