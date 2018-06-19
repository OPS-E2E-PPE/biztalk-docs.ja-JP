---
title: '手順 4: 作成、バッチ メッセージを受け入れるための受信ポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a37eb334-c4ae-40d1-a433-bf0ab39c0765
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56d1aa54639263e6741c6df89c3888b9b4120515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207610"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>手順 4: 作成、バッチ メッセージを受け入れるための受信ポート
このステップでは、作成し、受信のバッチを受信するポートを構成します。  
  
 要求-応答を (双方向) 作成するシナリオには、生成が含まれているためアプリケーションに受け入れられるように、バッチ内の個々 のメッセージの受信確認の受信ポート、します。 双方向のモードでは、受信パイプラインの前のメッセージの受信確認 (ACK) が生成されるまで、MLLP の受信アダプターは、新しい受信メッセージを受け入れません。  
  
## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>バッチ メッセージを受け付ける受信ポートを作成します。  
  
1.  開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開し、 **BizTalk アプリケーション 1**です。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。  
  
2.  右クリック**受信ポート****新規**、し、**要求-応答受信ポート**です。  

3.  **名前**、入力**Tutorial_2WayReceive**です。  

4.  選択**適用**、ポートをバインドし、選択**受信場所**です。  
  
5.  選択**新しい**です。  

6.  **名前**、入力**Tutorial_2WayReceive**です。

7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストからです。  
  
8. **[構成]** を選択します。 **MLLP トランスポートのプロパティ**、次を構成し、 **OK**です。  

    |プロパティ|目的|  
    |---|---|  
    |**接続再試行時間 (秒)**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>削除済みまたは閉じている接続の再接続を試行する前に待機する時間の上限。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。<br/><br/>既定値は、20 秒です。|
    |**によって開始される接続**| 始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>入力**ローカル**MLLP の受信場所をリモートの LOB サーバーへの接続を開始します。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモートの LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値は Remote です。| 
    |**接続名**|入力**2 ウェイ**です。|  
    |**ホスト名**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**です。|  
    |**ローカルのホスト名**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。 入力することも**localhost**です。|  
    |**[ポート]**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>設定**21000**です。|  
    |**ローカル ポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始される**は**リモート**です。 <br/><br/>設定**21000**です。|
    |**リモート ホスト**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。|  
    |**リモートのポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>リモート ホスト接続への TCP ポート番号を入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。<br/><br/>設定**21000**です。|  

9. 受信場所のプロパティで、次のように選択します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信ハンドラー**|選択**BizTalkServerApplication**ドロップダウン リストから|  
    |**受信パイプライン**|選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**|  
    |**送信パイプライン**|選択**BTAHL72XPipelines.BTAHL72XSendPipeline**|  

11. **[OK]** を選択して変更を保存します。  
  
12. 右クリックして、作成した受信場所を有効にし、**を有効にする**です。  
  
## <a name="next-step"></a>次の手順
[手順 5: メッセージを配信する送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)