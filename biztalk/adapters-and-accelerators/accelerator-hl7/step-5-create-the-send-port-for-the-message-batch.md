---
title: "手順 5: は、メッセージ バッチの送信ポートを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3176814481d98a7aa0e1e48abad9f20e887b17ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a>手順 5: メッセージのバッチの送信ポートを作成します。
この手順では、送信先パーティを作成するメッセージのバッチを配信する送信ポートを作成します。 これは、ファイル アダプターの種類に静的な一方向のポートです。 ここで、変換先 (\Tutorial_BatchMsgDrop) のファイルのフォルダーを指定する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ バッチ ファイルが削除されます。 ポートで送信するメッセージのバッチの種類を示すポートのフィルターを定義するとします。 フィルターは、Tutorial_BatchDest と OutboundBatch のメッセージの種類の変換先を指定します。  
  
> [!NOTE]
>  チュートリアルの第 2 部で使用する送信ポートを停止することによって、結果を簡略化できますチュートリアルのこの部分を実行する場合: **Tutorial_BTAHL7Drop**ポートを送信します。  
  
### <a name="to-create-the-send-port-for-the-message-batch"></a>メッセージ バッチの送信ポートを作成するには  
  
1.  [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理コンソールを右クリックして**送信ポート**、 をポイント**新規**、クリックして**静的な一方向送信ポート**です。  
  
2.  [送信ポートのプロパティ] ダイアログ ボックスで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Tutorial_BatchDest**です。|  
    |**型**|選択**ファイル**ドロップダウン リストからです。|  
    |**構成**|をクリックして**構成**FILE トランスポートのプロパティ ダイアログ ボックスを開きます。|  
  
3.  **FILE トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**コピー先フォルダー**|参照  **\<*ドライブ*: > \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\End エンドツー エンド Tutorial\Tutorial_BatchMsgDrop * *。 これは、ファイル システムまたはパブリックの共有の場所にパス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]メッセージ バッチを含んでいるファイルを記述します。|  
    |**ファイル名**|型**%MessageID%.txt** (拡張子 .txt に .xml 拡張子を置き換えます)。|  
    |**[コピー モード]**|選択**新規作成**です。|  
  
4.  **[OK]**をクリックします。  
  
5.  送信ポートのプロパティ] ダイアログ ボックスの**送信パイプライン**[ **BTAHL72XPipelines.BTAHL72XSendPipeline**です。  
  
6.  コンソール ツリーでクリックして**フィルター**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**プロパティ**|下のフィールドをクリックして**プロパティ**、し、 **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**ドロップダウン リストからです。|  
    |**演算子**|ままにして **==** 演算子とします。|  
    |**値**|型**Tutorial_BatchDest**です。|  
    |**グループ化**|選択**と**ドロップダウン リストからです。|  
    |**プロパティ**|選択**BTAHL7Schemas.BTAHL7MessageType**です。|  
    |**演算子**|ままにして **==** 演算子とします。|  
    |**値**|型**OutboundBatch**です。|  
  
7.  **Enter**キーを押します。 クリックしてダイアログ ボックスの下部にあるペインで、フィルター式の入力が正しいことを確認してください**OK**です。  
  
8.  BizTalk 管理コンソールで、次のように選択します。**送信ポート**、を右クリック**Tutorial_BatchDest**、順にクリック**開始**です。  
  
### <a name="to-associate-the-send-port-with-the-destination-party"></a>送信先パーティに送信ポートを関連付ける  
  
1.  [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]管理コンソールで、展開**パーティ**をクリックして**Tutorial_BatchDest**、し、右クリック**プロパティ**です。  
  
2.  [パーティのプロパティ] ダイアログ ボックスで、**送信ポート**コンソール ツリーでします。  選択**Tutorial_BatchDest**クリックしてドロップダウン リストから**OK**です。  
  
    > [!NOTE]
    >  同時実行制御違反が発生した場合中に、 **Tutorial_DestBatch**パーティの更新中で、[ **OK** ] ダイアログ ボックスを閉じます。 管理コンソールで、右クリック**BizTalk グループ**、 をクリックして**更新**、手順 1. と 2. を繰り返します。  
  
 進みます[手順 6: 受信確認のバッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)です。