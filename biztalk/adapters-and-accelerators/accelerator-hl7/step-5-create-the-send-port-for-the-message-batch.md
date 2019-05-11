---
title: 手順 5:メッセージ バッチの送信ポートの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4d69f21413e084ae81eda69827c079b39379bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287970"
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a>手順 5:メッセージ バッチの送信ポートを作成します。
この手順では、送信先パーティを作成するメッセージのバッチを配信する送信ポートを作成します。 これは、ファイル アダプターの種類を静的な一方向のポートです。 場所 (\Tutorial_BatchMsgDrop) 移行先のファイル フォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージのバッチ ファイルが削除されます。 ポートで送信するメッセージのバッチの種類を示すポートのフィルターを定義します。 フィルターには、Tutorial_BatchDest と OutboundBatch のメッセージの種類の変換先を指定します。  

> [!NOTE]
>  チュートリアルの第 2 部で使用する送信ポートを停止することで、結果を簡略化できます、チュートリアルのこの部分の実行中、: **Tutorial_BTAHL7Drop**ポートを送信します。  

### <a name="to-create-the-send-port-for-the-message-batch"></a>メッセージ バッチの送信ポートを作成するには  

1. 右クリックし、BizTalk Server 管理コンソールで**送信ポート**、 をポイント**新規**、 をクリックし、**静的な一方向送信ポート**。  

2. [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  


   |   プロパティ    |                              目的                               |
   |---------------|-----------------------------------------------------------------------|
   |   **名前**    |                     型**Tutorial_BatchDest**します。                      |
   |   **型**    |               選択**ファイル**ドロップダウン リストから。                |
   | **構成** | クリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。 |


3. **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   |        プロパティ        |                                                                                                                                                                           目的                                                                                                                                                                            |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **コピー先フォルダー** | 参照する **\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_BatchMsgDropのアクセラレータ**. これは、ファイル システムまたはパブリックの共有上の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ バッチを含んでいるファイルに書き込まれます。 |
   |     **[ファイル名]**      |                                                                                                                                         型 **%MessageID%.txt** (.txt 拡張子 .xml 拡張子を置き換えます)。                                                                                                                                          |
   |     **コピー モード**      |                                                                                                                                                                     選択**新規作成**です。                                                                                                                                                                      |


4. **[OK]** をクリックします。  

5. 送信ポートのプロパティ ダイアログ ボックスでの**送信パイプライン**、 **BTAHL72XPipelines.BTAHL72XSendPipeline**します。  

6. コンソール ツリーで、クリックして**フィルター**、し、次の操作を行います。  


   |   プロパティ   |                                                              目的                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **プロパティ** | 下のフィールドをクリックします。**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストから。 |
   | **[演算子]** |                                                    まま**==** 演算子として。                                                     |
   |  **[値]**   |                                                     型**Tutorial_BatchDest**します。                                                     |
   | **グループ化** |                                               選択**と**ドロップダウン リストから。                                                |
   | **プロパティ** |                                             選択**BTAHL7Schemas.BTAHL7MessageType**します。                                              |
   | **[演算子]** |                                                    まま**==** 演算子として。                                                     |
   |  **[値]**   |                                                       型**OutboundBatch**します。                                                        |


7. **Enter**キーを押します。 クリックしてダイアログ ボックスの下部にあるウィンドウで、フィルター式の入力が正しいことを確認します**OK**します。  

8. BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchDest**、 をクリックし、**開始**。  

### <a name="to-associate-the-send-port-with-the-destination-party"></a>送信先パーティに送信ポートを関連付ける  

1. BizTalk Server 管理コンソールで [**パーティ**、] をクリックして**Tutorial_BatchDest**、右クリックし、**プロパティ**します。  

2. パーティのプロパティ] ダイアログ ボックスで、[**送信ポート**コンソール ツリーでします。  選択**Tutorial_BatchDest**クリックしてドロップダウン リストから**OK**します。  

   > [!NOTE]
   >  同時実行制御違反が発生した場合に、 **Tutorial_DestBatch**パーティの更新中で、[ **[ok]** ] ダイアログ ボックスを閉じます。 管理コンソールで、右クリック**BizTalk グループ**、 をクリックして**更新**、し、手順 1. および 2. を繰り返します。  

   続行する[手順 6。受信確認のバッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)します。