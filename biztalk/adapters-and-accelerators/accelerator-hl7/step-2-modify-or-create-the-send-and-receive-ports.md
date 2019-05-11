---
title: 手順 2:変更または作成、送信ポートと受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8538bd8f67a78c77c0dca0a875c26ed169672e80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288609"
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a>手順 2:変更または作成、送信ポートと受信ポート
ファイルの送信と、バッチの受信ポートが必要で/バッチ アウト チュートリアル。 クリックした場合、 **Launch Tutorial**の Enterprise Edition のインストールの最後にあるボタン[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]これらのポートを作成する: Tutorial_BTAHL7Drop、という名前の送信ポートと受信ポート Tutorial_BTAHL7PickUp という名前です。 これらのポートがあれば、引き続き Tutorial_BTAHL7Drop 送信ポートを変更する必要があります。  

 場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セットアップでしたいない送信を作成の受信ポート、このトピックでは、「を作成する、BIBOTutorialPickup 受信ポート」手順を参照してこのトピックでも「を作成する、BIBOTutorialDrop 送信ポート」の手順を参照してください。  

### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a>Tutorial_BTAHL7Drop 送信ポートを変更するには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

3. クリックして**送信ポート**、右クリック**Tutorial_BTAHL7Drop**、順にクリックします**プロパティ**します。  

4. コンソール ツリーで、クリックして**フィルター**します。  

5. **フィルター**ウィンドウの選択の 2 番目の行で、 **BTAHL7Schemas.MessageClass**の**プロパティ**、 **==** の**演算子**、および種類**MessageClass2X**の**値**します。 **Enter**をクリックします。  

6. 設定**Group By**上、 **BTS します。ReceivePortName**の行を**または**、 をクリックし、 **OK**。  

7. Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理 ウィンドウで展開**プラットフォームの設定**、展開と**ホスト インスタンス**します。 右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。  

   > [!NOTE]
   >  Standard Edition をインストールした場合のみ、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]、しなかった場合、または、 **Launch Tutorial**を設定するときにボタン[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。  

### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a>Tutorial_BTAHL7Pickup、受信ポートと場所を作成するには  

1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  

2. 管理コンソールで  [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

3. 右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  

4. 受信ポートのプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_BTAHL7PickUp**します。  

5. をクリックして**適用**をクリックして、ポートのバインド**OK**します。  

6. 右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  

7. 受信ポートのダイアログ ボックスのをクリックして**Tutorial_BTAHL7PickUp**、順にクリックします**OK**します。  

8. 受信場所のプロパティ ダイアログ ボックスでの**名前**ボックスに「 **Tutorial_FileReceiveLoc**します。  

9. **トランスポート**セクションの**型**テキスト ボックス、ドロップダウン リストをクリックし、**ファイル**します。  

10. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  

11. ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  


    |      プロパティ      |                                                                                                                                                                         目的                                                                                                                                                                          |
    |--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **受信フォルダー** | 参照する**\<**<em>ドライブ</em>**\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7PickUp**します。 **注:** これは、パス、ファイル システムまたはパブリック共有上の場所にどこから[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は、ファイルを取得します。 |
    |   **ファイル マスク**    |                                                                                                                                                                      型 **\*.txt**します。                                                                                                                                                                       |


12. **[OK]** をクリックします。  

13. 受信場所のプロパティ ダイアログ ボックスで、次の手順を実行します。  


    |       プロパティ       |                      目的                       |
    |----------------------|-------------------------------------------------------|
    | **受信ハンドラー**  |    保持**BizTalkServerApplication**として選択します。     |
    | **受信パイプライン** | 選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**します。 |


14. **[OK]** をクリックします。  

15. BizTalk エクスプ ローラーで右クリックして**Tutorial_FileReceiveLoc**、 をクリックし、**を有効にする**します。  

### <a name="to-create-the-tutorialbtahl7drop-send-port"></a>Tutorial_BTAHL7Drop 送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |   プロパティ    |                                目的                                 |
   |---------------|---------------------------------------------------------------------------|
   |   **名前**    |                       型**Tutorial_BTAHL7Drop**します。                       |
   |   **型**    |                 選択**ファイル**ドロップダウン リストから。                  |
   | **構成** | クリックして**構成**を開く、 **FILE トランスポートのプロパティ** ダイアログ ボックス。 |


3. ファイル トランスポートのプロパティ ダイアログ ボックスで、次の手順を実行します。  


   |        プロパティ        |                                                                                                                                                                      目的                                                                                                                                                                       |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | 参照する**\<**<em>ドライブ</em>**:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンドのアクセラレータTutorial\Tutorial_BTAHL7Drop**します。 **注:** これは、ファイル システムまたはパブリックの共有上の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ファイルに書き込まれます。 |
   |     **[ファイル名]**      |                                                                                                                                          型 **%MessageID%.txt** (拡張機能は、txt、xml ではないことに注意してください)。                                                                                                                                          |


4. **[OK]** をクリックします。  

5. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**ドロップダウン リストから。  

6. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                       目的                        |
   |--------------|---------------------------------------------------------|
   | **プロパティ** | 選択**BTS します。ReceivePortName**ドロップダウン リストから。 |
   | **[演算子]** |              まま**==** 演算子として。              |
   |  **[値]**   |             型**Tutorial_BTAHL7PickUp**します。             |
   | **グループ化** |         選択**または**ドロップダウン リストから。          |
   | **プロパティ** |         選択**BTAHL7Schemas.MessageClass**します。          |
   | **[演算子]** |              まま**==** 演算子として。              |
   |  **[値]**   |                型**MessageClass2X**します。                 |


7. **Enter**をクリックします。 ダイアログ ボックスの下部にあるウィンドウで、フィルター式が正しいことを確認します。  

8. **[OK]** をクリックします。  

9. 管理コンソールで、**送信ポート**を右クリックして**Tutorial_BTAHL7Drop**、順にクリックします**開始**します。  

10. 展開**プラットフォームの設定**、 をクリックし、**ホスト インスタンス**します。 右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。  

    続行する[手順 3。テストのバッチ処理/バッチ アウト シナリオ](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)します。