You Wanna Read Me? Haha, If You Can! :)

**【 レール演奏補助ツール(仮称?) - Made by @Shamoji_SMM 】**

// 本ツールは基本的にフリーです。法律と任天堂の赦す限り、自由に紹介・利用・動画化・~~批評~~などしてもらって構いません。(自作発言とかはダメだよ！)

このツールは、スーパーマリオメーカー2(以下SMM2, マリメ)における「レール演奏」作成の補助を目的としたツールです。  
主にレール演奏を作り慣れている方向けのツールとなっておりますので、あしからず。  

レール演奏とはなんぞや、という方は以下の資料をご覧になることをおすすめします。  
・[ループ演奏入門(1)](https://www.youtube.com/watch?v=IE5-31xXOFE) (レール演奏の詳しい作り方が載ってます。)  
・[「レール演奏」の仕組み](https://www.youtube.com/watch?v=KGK65KVXegw&list=PLMuQzt5dSbFVWo_9oRgFnCzC1zqaGAwdr&index=1) (SMM1の情報が多いですが、いろんなレール演奏が載ってます。)  
・[ギャップ調整法の検証と考察](https://www.youtube.com/watch?v=r1Lp6UY5NIc) (後述するレール演奏のロジカルな集音方法について解説されています。)  
・他にも、YouTubeなどで「レール演奏」と検索すると色んなレール演奏が見れます。  

// このツールは多くの先人たちの研究の成果を利用させてもらっています。  
// 特に、レールループ生成は [レールループ周期表](https://twitter.com/fnjxbf0b5/status/1601536592879161345) by @fnjxbf0b5 を自動化したものになっております。  
// その他、マリメに関する様々な研究のおかげでツールを作成することができました。感謝です。  

以下、本ツールの使い方を簡単に紹介します。  
なお、単位や用語に関しては本ツールのページの下の方に載ってます。  


**1. BPMと符長**  

4分符長[f] に4分音符の長さを入れると、BPMと他の符長を計算してくれます。  
また、表の下のBPM で逆算できます。  
```
BPM計算の式:
  Beats Per Minutes = 3600 / 1拍の長さ
  3600 = 60seconds * 60frames = 1minutes
```


**2. 小節計算**  

拍子: n/m拍子, m分のn拍子  
長さ[f]: ループの長さ  


**3. レールループ生成**  

周期[f]: ループさせたいメロディの長さ。  

羽あり往復: 羽ありブロック(音符ブロックやレンガブロックなど)の往復型レールループ。空中飛ばし(断線)なし。偶数周期しか作れない。  
羽あり特殊: 特殊型。断線あり。168f以上のあらゆる周期のループを作成できる優れもの。  
羽あり周回: 断線なしの周回型、つまり単純閉曲線。往復型よりは作れる周期が多い。  
羽なし往復: 羽なしブロックの往復型。断線などもちろんない。作れる周期は限定的。  
羽なし周回: 後日作ります。  

特殊型以外は断線を含まないため水中でも使用できます。  
そして、この機能はレール演奏以外でも使えます。  
例えば、バーナーの周期は372fなので、372と入力して生成するとバーナーと同じ周期のレールループが作成できます。  
~~バーナーの周期きれいすぎない？~~  


**4. レールループ周期確認**  

直線, 斜め, 曲線, うるうの本数を入力して周期を計算します。  
羽あり往復型でまっすぐな直線3本を含むループの場合、うるうの欄には1を入れてください。  
(うるうは往復ではなく片道での本数。)  

ちなみに、羽なしのうるう距離発生条件は直線2本...ではありません。  
正確には、「まっすぐな直線3本でうるう距離2」です(もちろん直線2本でも1発生します)。  
つまり、羽ありが 21→21→22 なのに対し、羽なしは 42→43→43 です。  
一見おかしく感じますが、計算するとちゃんと羽ありの倍の遅さになってます。  


**5. 表計算**  

[解説動画](https://www.youtube.com/watch?v=DFh_rsFVZ8c)  

読み込みタイプ:  
  開始画面(全て同時): ゲームスタート時、ドアや土管から出たときに読み込まれるエリアでの集音。  
  自由落下: 縦エリアでプレイヤーが終端速度で落下して集音。  
  縦スクロール: 縦エリアでスクロールして集音。上向きが正。  
    平均スクロール遅度: 小数で入力。下記のスクロール遅度表を参考。(遅度: f/b, 1マス進むのにかかる時間。)  
  横スクロール: 横エリアでスクロールして集音。右向きが正。  
    カスタム: 表の横スク遅延[f] に1bごとに遅度を入力。  
    平均遅度: 平均スクロール遅度[f/b] に小数で入力。  
    遅度周期: スクロール遅度周期[f/b] にコンマ区切りで入力(例: 6, 7, 6, 7, 6)。負の場合は(-2, -3)のように。  

着線パターン:  
  カスタム: 表のxズレ[f] に直接入力。  
  1~4: 下記の画像参照。  

基準音階: LowC ~ HiD# までで選択。「基準」とは、集音の左端の音符のことを指す。  
音色: お好みで。  
演奏, 演奏停止: 数値を入力し終わった後に押すと演奏できます。  

遅延入力方法:  
  それぞれの符長: 音の並びのまま、それぞれの音の長さをn分符 もしくは符長[f] に入力。8分間隔で音が並んでいる場合、8, 8, 8, 8... となる。  
  累計遅延: それぞれの音符の演奏までにかかる時間を累計遅延[f] に入力。順番は並び替え可。171bpmで8分間隔で音を鳴らす場合、0, 8, 16, 24... や、0, 24, 8, 16... のように入力できる。  

**表**:  
  番号: 1~100。  
  メモ: 小節頭のマークなど書くと便利。  
  n分符: 音符の長さ[分音符]。8+16, 4-32 のように入力できる(8分と16分の加算, 4分から32分を引いた長さ)。  
  符長[f]: 4分符長[f] の値によって自動で入力される。音符の長さ[f]。  
  xズレ[f]: 1つ左の列まで移動するのにかかる時間。基本10or11。基準は0。  
  (横スク遅延[f]): 1つ左の列からの、その音符を読み込むのにかかる時間。1マスの移動にかかる時間。  
  yズレ(b): 基準音符ブロックからのy方向の距離。同じ高さなら0、上なら1, 2, 3...、下なら-1, -2, -3...。自由落下の場合入力しなくてよい。  

  結果[f]: 集音するときに必要な遅延。1番左の欄に調整用の値(50~120ぐらい)。  
  高さ[b]: 着線レールからの高さ。基準の高さのみ入力。  

  配置: その列の音符が配置可能かどうか。(◎一致, ○誤差, △もっと誤差, ×不可)。  
  代入: 後述する縦集音配置生成に値を代入して計算。  

更新: 入力された値をもとに新しく計算。
検証: 結果が配置可能かどうかを検証。配置 に出力され、◎, ○, △, ×の個数もカウント。  

終速度度を使用: 集音する際、1番下の縦レールから8b以上あける。おすすめしない。  


**6. 縦集音配置生成**  

狙いの値[f]: 表計算の結果[f] の値を入力。この値は、何も調整せず(縦レールを追加せず)下向きに音符ブロックを落としたときと比べての遅延。  
着線レールとの距離[b]: 表計算の高さ[b] の値を入力。終端速度を使用する場合、入力しなくてよい。  

並び替え: 出てきた配置たちを並び替え。終端速度を使用する場合は"↓長さ 短い順"、それ以外は"↑長さ 短い順"がおすすめ(スペースを削減できるため)。  

↓or↑: 音符ブロックの進行方向。  
-: -の前が上向きオプション、後が下向きオプション。  
R: レールの本数。上オプションがRで終わる場合はレールの上端を閉じる。  
G: ギャップ。レール間の距離。  
F: 上オプションで上投げ。レールの上端を開く。  

一致: ±0, 誤差: ±1, もっと誤差: ±2。  

出てきた配置テキスト(delay/doun/up/display)をクリックすると左に画像が出ます。便利です。  

// 一致だからと言って必ずズレがないとは言い切れません...  
// 精度向上に努めます。(データの誤り見つけたら教えてね！)  

表計算の順番で配置を並べることにより集音できます。  


**7. 画像**  

レールループの作り方、縦集音の配置方法、高さの数え方、着線パターンが載ってます。  


**8. スクロール遅度表**  

[一部参考](https://www.youtube.com/watch?v=3VlLrf_5KvA)  

横スク、縦スクの平均遅度と遅度周期。  
この値を表計算で使えます。  


**9. グローバル音源配置集**  

たぶん便利なグローバル音源たちです。  
スキンごとに使用可能なパーツが載っています。  

追加してほしいものがあったら教えてください。  

**10. 雑記 / 参考文献・資料**  

たぶん、きっと有益なことは書いていません。  

**用語と単位集**  

ここで定めているものです。物好きな人はどうぞ。  
うるう距離の説明が難しい。  

**役立つかもしれないTips**  

役立たないかもしれません。  


**参考文献・資料**  

多くの方々の研究のおかげでこのツールを作成することができました。  
心より感謝いたします。  



何かわからないことがあればご気軽に訊いてください。
