---
title: '手順 4: 作成、受信ポート ADT クエリ メッセージの受け入れの |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: 8bef032f-5f43-4d36-b88f-ed81f27bb803
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acda59342c8469810a4645521c395c458fe5d73e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000755"
---
# <a name="step-4-create-the-receive-port-for-accepting-adt-query-messages"></a>手順 4: 作成、ADT クエリ メッセージを受け入れるための受信ポート
入学、放電、によって送信されるクエリ メッセージの受信場所を指定する受信ポートを作成して、転送 (ADT) システムです。 次の手順を使用してクエリを受け付ける受信ポートを作成する (QRY ^ Q01 メッセージ) 最小限の下位レイヤー プロトコル (MLLP) アダプターを使用して ADT system から。  

## <a name="create-the-adtreceiveport-receive-port"></a>作成、ADT_ReceivePort 受信ポート  

1. 開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

2. 右クリックして**受信ポート**を選択します**新規**、し、**要求-応答受信ポート**します。  

3. **名前**、入力**ADT_ReceivePort**します。  

4. 選択**適用**、ポートをバインドし、選択**受信場所**します。  

5. 選択**新しい**します。 

6. **名前**、入力**ADT_Receive**します。  

7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストから。  

8. **[構成]** を選択します。 **MLLP トランスポート プロパティ**、次を構成し、 **OK**します。  


   |           プロパティ           |                                                                                                                                                                                                     目的                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **接続再試行時間 (秒)** |                                                                 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>削除されたか、閉じられた接続の再接続を試みる前に待機する時間の上限値。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。<br/><br/>既定値は、20 秒です。                                                                  |
   | **によって開始された接続**  | 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>入力**ローカル**MLLP 受信リモート LOB サーバーへの接続を開始する場所。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモート LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値はリモートです。 |
   |     **接続名**      |                                                                                                                                                                                             入力**ADT_ReceiveMLLP**します。                                                                                                                                                                                             |
   |        **ホスト名**         |                                                                                                                                              固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**します。                                                                                                                                               |
   |     **ローカル ホスト名**      |                                                                            以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。 入力することも**localhost**します。                                                                             |
   |           **[ポート]**           |                                                                                                                                                固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>設定**22000**します。                                                                                                                                                |
   |        **ローカル ポート**        |                                                                                       以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始された**は**リモート**します。 <br/><br/>設定**22000**します。                                                                                        |
   |       **リモート ホスト**        |                                                                                                   以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。                                                                                                    |
   |       **リモート ポート**        |                                                                                      以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>リモート ホスト接続の TCP ポート番号を入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。<br/><br/>設定**22000**します。                                                                                       |


9. 設定、**受信ハンドラー**に**BizTalkServerApplication**します。  

10. 設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**します。  

11. 設定、**送信パイプライン**に**PassThruTransmit**します。

12. **[OK]** を選択して変更を保存します。  

13. 右クリックし、作成した受信場所を有効にし、**を有効にする**します。  

## <a name="next-step"></a>次の手順  
[手順 5: HIS メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)