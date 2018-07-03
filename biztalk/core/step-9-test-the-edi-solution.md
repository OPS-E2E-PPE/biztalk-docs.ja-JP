---
title: '手順 9: EDI ソリューションのテスト |Microsoft Docs'
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
ms.openlocfilehash: ab6da406d2de066f9a1a7f4a99576ca9c2fa14d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979675"
---
# <a name="step-9-test-the-edi-solution"></a>手順 9: EDI ソリューションをテストします。
![手順 9 の 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")  
  
 このトピックでは、受信処理をテストし、処理情報に関する EDI インターチェンジ状態レポートを表示します。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="testing-the-solution"></a>ソリューションのテスト  
  
1. Windows エクスプローラーで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations に移動します。 コピー、 **SamplePO.txt**ファイル。  
  
2. 貼り付け、 **SamplePO.txt**ファイルを[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer tutorial \processedi_testlocations\scenario a \fromthem フォルダー。  
  
3. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem フォルダーに移動します。 フォルダに出力テキスト ファイルが含まれていることを確認します。  
  
4. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toOrderSystem の出力ファイルと、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations の SamplePO.txt 入力ファイルを開きます。 出力メッセージのデータが元のデータに対応していることを確認**SamplePO.txt**ファイル。  
  
   > [!NOTE]
   >  Visual Studio で Inbound4010850_to_OrderFile.btm ファイルを開いて、マッピングをチェックすることにより、出力ファイルのデータが入力ファイルのデータから変換されているかどうかを確認できます。  
  
5. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\ProcessEDI_TestLocations\Scenario A\toTHEM_997 フォルダーに移動します。 ST01 データ要素が "997" である出力 997 受信確認テキスト ファイルがこのフォルダに含まれていることを確認します。  
  
6. コンソール ツリーで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、をクリックして**BizTalk グループ**します。 右側のウィンドウの下部には、次のようにクリックします。 **EDI インターチェンジと関連する ACK の状態**します。  
  
7. クエリ式での演算子を変更する、**状態**フィールドを**Equals**を変更して、**値**フィールドを**状態**フィールドを**すべて**します。 削除、**インターチェンジの日時フィールド**(行を選択し、キーのボードの DEL キーを押します)。  
  
8. クリックして**クエリを実行**します。  
  
9. 状態レポートに 2 つのメッセージが表示されていることを確認します。1 つは THEM (Fabrikam) から US (OrderSystem) (850 メッセージ) への受信方向であり、もう 1 つは US (OrderSystem) から THEM (Fabrikam) (997 受信確認) への送信方向です。  
  
10. THEM から US へのメッセージをダブルクリックします。 **インターチェンジの状態と確認の詳細** ダイアログ ボックスで、右側のウィンドウで、インターチェンジの詳細が表示されることを確認します。  
  
11. クリックして**機能確認**します。 受信確認のレポート詳細が右ペインに表示されていることを確認します。  
  
12. [インターチェンジの状態と確認の詳細] ダイアログ ボックスを閉じます。  
  
13. **インターチェンジ/確認の状態**ウィンドウで、THEM から US へのメッセージを右クリックし、クリックして**トランザクション セットの詳細**します。 エントリを右クリックして、**クエリ結果**ペイン、およびクリック**トランザクション セット**します。 トランザクション セット データが表示されることを確認、**メッセージの詳細** ダイアログ ボックス。 Windows エクスプローラーを使用して、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\ProcessEDI_TestLocations の SamplePO.txt ファイルを開きます。 トランザクション セットであることを確認、**メッセージの詳細** ダイアログ ボックスは、インターチェンジとグループ ヘッダーとトレーラーせず、入力メッセージと同じです。  
  
## <a name="next-steps"></a>次の手順  
 これで、EDI インターフェイス開発チュートリアルは完了です。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 2: EDI インターフェイス開発チュートリアル](../core/tutorial-2-edi-interface-developer-tutorial.md)   
 [手順 1: EDI インターフェイス開発チュートリアルのための準備](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)