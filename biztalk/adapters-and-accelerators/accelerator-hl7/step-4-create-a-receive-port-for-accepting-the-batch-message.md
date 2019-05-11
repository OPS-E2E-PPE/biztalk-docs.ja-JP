---
title: 手順 4:作成、受信ポートのバッチ メッセージを受け入れる |Microsoft Docs
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
ms.openlocfilehash: 4fca10f31c3de2d82b769cb63a732c7c144a465a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288207"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>手順 4:作成、受信ポートのバッチ メッセージを受け入れる
この手順では、作成し、受信のバッチを受信するポートを構成します。  

 作成要求-応答 (双方向) の受信ポート、シナリオには生成が含まれていますので、アプリケーションに受け入れ、バッチ内の個々 のメッセージの受信確認。 双方向のモードでは、受信パイプラインの前のメッセージの受信確認 (ACK) が生成されるまで、MLLP 受信アダプターは、新しい着信メッセージを受け入れません。  

## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>バッチ メッセージを受け入れるための受信ポートを作成します。  

1. 開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

   > [!NOTE]
   >  BizTalk Server 管理コンソールで開くこともできますから Visual Studio 内でクリックして**BizTalk Server 管理**で、**ツール**メニュー。  

2. 右クリックして**受信ポート**を選択します**新規**、し、**要求-応答受信ポート**します。  

3. **名前**、入力**Tutorial_2WayReceive**します。  

4. 選択**適用**、ポートをバインドし、選択**受信場所**します。  

5. 選択**新しい**します。  

6. **名前**、入力**Tutorial_2WayReceive**します。

7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストから。  

8. **[構成]** を選択します。 **MLLP トランスポート プロパティ**、次を構成し、 **OK**します。  


   |           プロパティ           |                                                                                                                                                                                                     目的                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **接続再試行時間 (秒)** |                                                                 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>削除されたか、閉じられた接続の再接続を試みる前に待機する時間の上限値。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。<br/><br/>既定値は、20 秒です。                                                                  |
   | **によって開始された接続**  | 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>入力**ローカル**MLLP 受信リモート LOB サーバーへの接続を開始する場所。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモート LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値はリモートです。 |
   |     **接続名**      |                                                                                                                                                                                                  入力**2 ウェイ**します。                                                                                                                                                                                                   |
   |        **ホスト名**         |                                                                                                                                              固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**します。                                                                                                                                               |
   |     **ローカル ホスト名**      |                                                                            以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。 入力することも**localhost**します。                                                                             |
   |           **[ポート]**           |                                                                                                                                                固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>設定**21000**します。                                                                                                                                                |
   |        **ローカル ポート**        |                                                                                       以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始された**は**リモート**します。 <br/><br/>設定**21000**します。                                                                                        |
   |       **リモート ホスト**        |                                                                                                   以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。                                                                                                    |
   |       **リモート ポート**        |                                                                                      以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>リモート ホスト接続の TCP ポート番号を入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。<br/><br/>設定**21000**します。                                                                                       |


9. 受信場所のプロパティで、次のように選択します。  


   |       プロパティ       |                         目的                          |
   |----------------------|-------------------------------------------------------------|
   | **受信ハンドラー**  | 選択**BizTalkServerApplication**ドロップダウン リストから |
   | **受信パイプライン** |    選択**BTAHL72XPipelines.BTAHL72XReceivePipeline**     |
   |  **送信パイプライン**   |      選択**BTAHL72XPipelines.BTAHL72XSendPipeline**      |


10. **[OK]** を選択して変更を保存します。  

11. 右クリックし、作成した受信場所を有効にし、**を有効にする**します。  

## <a name="next-step"></a>次の手順
[手順 5:メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)