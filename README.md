# IRAD (Image Recognition Action Decision)

<!-- IRADは学習用データと現在の映像データを画像認識して得られたテキストを何らかの形式で保持し、長期的な目的が一致したテキストデータをもとに将来の大まかな短期的な目的を決定する。

上記で決定した短期的な目的と現在の状況が類似している学習データを元に将来の行動計画を決定する。
これは再帰的に処理することで次元が小さくなり、行動計画が具体的になっていく。

現在の状況が変化した場合はそれに伴って次元内の行動計画を変更する。
これも再帰的に処理することで、必要な場合は大まかな行動計画も変更することができる。

これらの行動計画テキストと同時にその時点での自身またはそれに関するステータスを保持しておく。
目的と現在の状況が類似しているか、ステータスも含めて判断する。

IRADは、学習用データと現在の映像データを画像認識して得られたテキストを保持し、長期的な目的が一致したテキストデータをもとに将来の大まかな短期的な目的を決定します。 -->


### IRADの動作手順：
- ##### 学習用データと現在の映像データを画像認識してテキストに変換する。
- ##### 短期的な目的を決定するために、長期的な目的と類似した学習データを選択する。
- ##### 選択した学習データを元に、短期的な目的を決定する。これを再帰的に処理することで、行動計画が具体的になっていく。
- ##### 現在の状況が変化した場合は、それに応じて行動計画を変更する。再帰的な処理により、必要に応じて大まかな行動計画も変更できる。

IRADはこれらの行動計画テキストと同時に自身が取得した過去の記憶や現在のステータスなど、様々な要素を加味して目的と現在の状況が類似しているか判断する。

テキスト形式で行動計画を生成することで、OCR等の文字認識を併用することができる。

### IRADを実現するにあたって:
- ##### 必要なライブラリ:
    - ###### 画像認識
    - ###### 文字認識

    上記を高精度かつ高速で処理する必要がある。
    二つを併用できるライブラリが望ましい。
    画像内のどの位置に物体があるか、なども取得する必要がある。
- ##### テキストの行動計画通りに行動するよう学習したモデル
    次元の最深部まで計画を生成することができれば "テキストの行動計画通りに行動するよう学習したモデル" は必要ないが、計算量を削減するためある程度の行動計画を生成したのちそれに沿って動作するモデルが必要。
- ##### データの類似度を測る
- ##### これまで収集したデータの効率的な蓄積、利用

### テキスト形式で行動計画を立てる理由:
- 文字認識を容易に扱える
- 文章をうまく加工することで人間が持っているルールを簡単に落とし込める
- AIがどのような計画を立てて、どのように行動するのかを見ることができる。
- 将来の適切な行動計画を教えてくれる人間の補助的なものにも応用できる。