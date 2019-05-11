---
title: 手順 4:作成の受信ポートの受け入れ ADT ^ A03 メッセージ MLLP アダプターを使用して ADT システムから |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports
- end-to-end tutorial, receive ports
- creating, receive ports
ms.assetid: 3c4192d5-d011-48b0-a3f9-47c5225780ee
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7068e7964f44947c23829af41cf24243889673ed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288322"
---
# <a name="step-4-create-the-receive-port-for-accepting-adta03-messages-from-adt-systems-using-the-mllp-adapter"></a>手順 4:作成の受信ポートの受け入れ ADT ^ A03 メッセージ MLLP アダプターを使用して ADT システムから
受信ポートを使用して、受信メッセージの受信場所を指定します。 次の手順を使用して ADT を受け付ける受信ポートを作成する ^ A03 メッセージ MLLP アダプターを使用して ADT System から。  

## <a name="create-the-receive-port"></a>受信ポートの作成  

1. 開いている**BizTalk Server 管理**、展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**します。  

   > [!NOTE]
   >  BizTalk Server 管理コンソールで開くこともできますから Visual Studio 内でクリックして**BizTalk Server 管理**で、**ツール**メニュー。  

2. 右クリックして**受信ポート**を選択します**新規**、し、**一方向の受信ポート**します。  

3. **名前**、入力**Tutorial_1WayReceive**します。  

4. 選択**適用**、ポートをバインドし、選択**受信場所**します。  

5. 選択**新しい**します。  

6. **名前**、入力**Tutorial_MLLPReceive**します。  

7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストから。  

8. **[構成]** を選択します。 **MLLP トランスポート プロパティ**、次を構成し、 **OK**します。  


   |           プロパティ           |                                                                                                                                                                                                     目的                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **接続再試行時間 (秒)** |                                                                 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>削除されたか、閉じられた接続の再接続を試みる前に待機する時間の上限値。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。<br/><br/>既定値は、20 秒です。                                                                  |
   | **によって開始された接続**  | 以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>入力**ローカル**MLLP 受信リモート LOB サーバーへの接続を開始する場所。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモート LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値はリモートです。 |
   |     **接続名**      |                                                                                                                                                                                                  入力**1Way**します。                                                                                                                                                                                                   |
   |        **ホスト名**         |                                                                                                                                              固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**します。                                                                                                                                               |
   |     **ローカル ホスト名**      |                                                                            以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]します。 入力することも**localhost**します。                                                                             |
   |           **[ポート]**           |                                                                                                                                              固有[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>既定値は**11000**します。                                                                                                                                              |
   |        **ローカル ポート**        |                                                                                     以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始された**は**リモート**します。 <br/><br/>既定値は**11000**します。                                                                                      |
   |       **リモート ホスト**        |                                                                                                   以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。                                                                                                    |
   |       **リモート ポート**        |                                                                                                    以降では新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]します。 <br/><br/>リモート ホスト接続の TCP ポート番号を入力します。 該当する場合に**によって接続が開始された**に設定されている**ローカル**します。                                                                                                    |


9. 設定、**受信ハンドラー**に**BizTalkServerApplication**します。  

10. 設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**します。  

11. **[OK]** を選択して変更を保存します。  

12. 右クリックし、作成した受信場所を有効にし、**を有効にする**します。  

## <a name="next-step"></a>次の手順  
[手順 5:ファイル アダプターを使用して ADT System に受信確認を配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)