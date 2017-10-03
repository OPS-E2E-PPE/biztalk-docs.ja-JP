---
title: "手順 4: 作成、ADT クエリ メッセージを受け入れるための受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: interrogative tutorial, receive ports
ms.assetid: 8bef032f-5f43-4d36-b88f-ed81f27bb803
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 301215ea32b992516bfead3cd77ecdb009087bb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-the-receive-port-for-accepting-adt-query-messages"></a>手順 4: 作成、ADT クエリ メッセージを受け入れるための受信ポート
受付、放電、によって送信されるクエリ メッセージを受信する場所を指定する受信ポートを作成して転送 (ADT) のシステムです。 次の手順を使用してクエリを受け入れるための受信ポートを作成 (クエリ ^ Q01 メッセージ) 最小下位層プロトコル (MLLP) アダプターを使用して、ADT システムからです。  
  
## <a name="create-the-adtreceiveport-receive-port"></a>作成、ADT_ReceivePort 受信ポート  
  
1.  開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開し、 **BizTalk アプリケーション 1**です。  
  
2.  右クリック**受信ポート****新規**、し、**要求-応答受信ポート**です。  
  
3.  **名前**、入力**ADT_ReceivePort**です。  
  
4.  選択**適用**、ポートをバインドし、選択**受信場所**です。  
  
5.  選択**新しい**です。 
  
6.  **名前**、入力**ADT_Receive**です。  

7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストからです。  
  
8. **[構成]**を選択します。 **MLLP トランスポートのプロパティ**、次を構成し、 **OK**です。  
  
    |プロパティ|目的|  
    |---|---|  
    |**接続再試行時間 (秒)**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>削除済みまたは閉じている接続の再接続を試行する前に待機する時間の上限。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。<br/><br/>既定値は、20 秒です。|
    |**によって開始される接続**| 始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>入力**ローカル**MLLP の受信場所をリモートの LOB サーバーへの接続を開始します。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモートの LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値は Remote です。| 
    |**接続名**|入力**ADT_ReceiveMLLP**です。|  
    |**ホスト名**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**です。|  
    |**ローカルのホスト名**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。 入力することも**localhost**です。|  
    |**[ポート]**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>設定**22000**です。|  
    |**ローカル ポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始される**は**リモート**です。 <br/><br/>設定**22000**です。|
    |**リモート ホスト**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。|  
    |**リモートのポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>リモート ホスト接続への TCP ポート番号を入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。<br/><br/>設定**22000**です。|  

9. 設定、**受信ハンドラー**に**BizTalkServerApplication**です。  
  
10. 設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。  

11. 設定、**送信パイプライン**に**PassThruTransmit**です。
  
11. **[OK]** を選択して変更を保存します。  
  
12. 右クリックして、作成した受信場所を有効にし、**を有効にする**です。  

## <a name="next-step"></a>次の手順  
[手順 5: 作成、彼のメッセージを受け入れるための受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)