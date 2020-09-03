﻿# ミニラボ: VNET ピアリング

**注**: このミニラボには、2 つの仮想ネットワークが必要です。 

**1 番目の仮想ネットワークの VNET ピアリングを構成する**

1. [https://portal.azure.com ](https://portal.azure.com/)でAzure portal にサインインし、最初の仮想ネットワークを選択します。

2. 「**設定**」 で、 「**ピアリング**」 を選択します。

3. 「**+ 追加**」 を選択します。

    + 1 番目の仮想ネットワーク ピアリングの 「**名前**」 を指定します。例としては「VNet1toVNet2」です。 

    + 「**仮想ネットワーク**」 ドロップダウンで、ピアリングする 2 番目の仮想ネットワークを選択します。 

    + リージョンに注意してください。これは VPN Gateway を設定するときに必要になります。 

    + 2 番目の仮想ネットワーク ピアリングの名前を指定します。例としては「VNet2toVNet1」です。 

    + 情報アイコンを使用して、ネットワーク アクセス、転送トラフィック、ゲートウェイ通過設定をレビューします。

    + 「**ゲートウェイ転送を許可する**」 チェック ボックスをオンにします。仮想ネットワークにゲートウェイが存在しないことを示すエラーを確認します。 

    + 「**ゲートウェイ転送を許可する**」 チェック ボックスがオフになっていることを確認します。

    + 「**OK**」 をクリックして設定を保存します。

**VPN Gateway を構成する**

1. 「**Azure portal**」で、 「**仮想ネットワーク ゲートウェイ**」を検索します。

2. 「**+ 追加**」 を選択します。

    + 仮想ネットワーク ゲートウェイの**名前**を指定します。例としては「VNet1Gateway」です。

    + ゲートウェイが 1 番目の仮想ネットワークと同じリージョンにあることを確認します。

    + 「**仮想ネットワーク**」 ドロップダウンで、1 番目の仮想ネットワークを選択します。

    + 「**パブリック IP アドレス**」 領域で、 「**新規作成**」 を選択し、IP アドレスに名前を付けます。

    + 「**作成とレビュー**」 をクリックします。検証エラーがあれば対処します。

    + 「**作成**」 をクリックします。 

3. 通知を監視して、ゲートウェイが正常に作成されたことを確認します。

**ゲートウェイ通過を許可する**

1. 「**Azure ポータル**」 で、1 番目の仮想ネットワークに戻ります。 

2. 「**概要**」 ブレードで、VPN Gateway 用の新しい 「**接続デバイス**」 があることを確認します。

3. ゲートウェイを選択し、ヘルス チェックを実行してアクセス統計をレビューできることを確認します。 

4. 前のページに戻り、 「**設定**」 の下の 「**ピアリング**」 を選択します。

    + ピアリングを選択し、 「**ゲートウェイの転送の許可**」 を有効にします。前のエラーが解決されたことを確認します。 

    + この選択を行った後に, 「**リモートゲートウェイの使用**」 は無効になることがわかります。 

5. 変更を**保存**します。 

**2 番目の仮想ネットワークの VNET ピアリングを確認する**

1. 「**Azure portal**」 で 2 番目の仮想ネットワークを選択します。 

2. 「**設定**」 で、 「**ピアリング**」 を選択します。

3. ピアリングが自動的に作成されていることがわかります。この名前は、1 番目の仮想ネットワーク ピアリングを構成したときに指定した名前です。 

4. 「**ピアリングの状態**」 が 「**接続済み**」 になっていることがわかります。

5. そのピアリングをクリックします。

    + 「**ゲートウェイ転送を許可**」 を選択できないことを確認します。

    + 情報アイコンを使用して、 「**リモートゲートウェイを使用**」 設定をレビューします。

6. 変更を 「**破棄**」 します。 

 