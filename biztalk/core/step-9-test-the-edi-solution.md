---
title: 手順 9:EDI ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7a44e0f-496c-462f-bf03-1c2f842d13b6
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2d07bc0d28bf7d983a70c2f5ec7ee5e0329da714
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244225"
---
# <a name="step-9-test-the-edi-solution"></a>手順 9:EDI ソリューションをテストします。
![手順 9 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 このトピックでは、受信、処理をテストし、情報を処理するため、EDI インターチェンジの状態レポートを表示します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="testing-the-solution"></a>ソリューションのテスト  
  
1. Windows エクスプ ローラーで、移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations します。 コピー、 **SamplePO.txt**ファイル。  
  
2. 貼り付け、 **SamplePO.txt**ファイルを[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem フォルダー。  
  
3. 移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \toordersystem フォルダー。 フォルダーに出力テキスト ファイルが含まれていることを確認します。  
  
4. 出力ファイルを開き[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \toordersystem の SamplePO.txt 入力ファイル[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations します。 出力メッセージのデータが元のデータに対応していることを確認**SamplePO.txt**ファイル。  
  
   > [!NOTE]
   >  出力ファイル内のデータが、Visual Studio で Inbound4010850_to_OrderFile.btm ファイルを開き、マッピングの確認入力ファイル内のデータから変換されたことを確認することができます。  
  
5. 移動、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi インターフェイス Developer tutorial \processedi_testlocations\scenario a \tothem_997 フォルダー。 ST01 データ要素の「997」出力 997 受信確認 txt ファイルがフォルダーに含まれていることを確認します。  
  
6. コンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk グループ**します。 右側のウィンドウの下部には、次のようにクリックします。 **EDI インターチェンジと関連する ACK の状態**します。  
  
7. クエリ式での演算子を変更する、**状態**フィールドを**Equals**を変更して、**値**フィールドを**状態**フィールドを**すべて**します。 削除、**インターチェンジの日時フィールド**(行を選択し、キーのボードの DEL キーを押します)。  
  
8. クリックして**クエリを実行**します。  
  
9. THEM (Fabrikam) から US (OrderSystem) (850 メッセージ)、US (OrderSystem) から THEM (Fabrikam) (997 受信確認) への送信方向の受信の方向に 1 つの状態レポートに 2 つのメッセージが表示されることを確認します。  
  
10. THEM から US へのメッセージをダブルクリックします。 **インターチェンジの状態と確認の詳細** ダイアログ ボックスで、右側のウィンドウで、インターチェンジの詳細が表示されることを確認します。  
  
11. クリックして**機能確認**します。 右側のウィンドウで、受信確認のレポートの詳細が表示されることを確認します。  
  
12. インターチェンジ状態と確認の詳細 ダイアログ ボックスを閉じます。  
  
13. **インターチェンジ/確認の状態**ウィンドウで、THEM から US へのメッセージを右クリックし、クリックして**トランザクション セットの詳細**します。 エントリを右クリックして、**クエリ結果**ペイン、およびクリック**トランザクション セット**します。 トランザクション セット データが表示されることを確認、**メッセージの詳細** ダイアログ ボックス。 Windows エクスプ ローラーの SamplePO.txt ファイルを開く[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \processedi_testlocations します。 トランザクション セットであることを確認、**メッセージの詳細** ダイアログ ボックスは、インターチェンジとグループ ヘッダーとトレーラーせず、入力メッセージと同じです。  
  
## <a name="next-steps"></a>次の手順  
 EDI インターフェイス開発チュートリアルを完了しました。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)   
 [ステップ 1: EDI インターフェイス開発チュートリアルを準備します。](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)