---
title: '手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ |Microsoft ドキュメント'
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
ms.openlocfilehash: 865675e12609beea4c909d19a74d3e0ec4f38715
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207738"
---
# <a name="step-4-create-the-receive-port-for-accepting-adta03-messages-from-adt-systems-using-the-mllp-adapter"></a>手順 4: 作成、ADT を受け入れるための受信ポート ^ MLLP アダプターを使用して ADT システムから A03 メッセージ
受信ポートを使用して、受信メッセージの受信場所を指定します。 ADT を受け付ける受信ポートを作成する次の手順に従います ^ MLLP アダプターを使用して、ADT システムから A03 メッセージ。  
  
## <a name="create-the-receive-port"></a>受信ポートの作成  
  
1.  開いている**BizTalk Server 管理コンソール**、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、展開し、 **BizTalk アプリケーション 1**です。  
  
    > [!NOTE]
    >  BizTalk Server 管理コンソール開くこともできますから Visual Studio 内をクリックして**BizTalk Server 管理コンソール**で、**ツール**メニュー。  
  
2.  右クリック**受信ポート****新規**、し、**一方向の受信ポート**です。  
  
3.  **名前**、入力**Tutorial_1WayReceive**です。  
  
4.  選択**適用**、ポートをバインドし、選択**受信場所**です。  
  
5.  選択**新しい**です。  
  
6.  **名前**、入力**Tutorial_MLLPReceive**です。  
  
7. **トランスポート**セクションで、**型**、し、 **MLLP**ドロップダウン リストからです。  
  
8. **[構成]** を選択します。 **MLLP トランスポートのプロパティ**、次を構成し、 **OK**です。  
  
    |プロパティ|目的|  
    |---|---|  
    |**接続再試行時間 (秒)**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>削除済みまたは閉じている接続の再接続を試行する前に待機する時間の上限。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。<br/><br/>既定値は、20 秒です。|
    |**によって開始される接続**| 始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>入力**ローカル**MLLP の受信場所をリモートの LOB サーバーへの接続を開始します。 これは、新しいオプションです。<br/><br/>入力**リモート**MLLP の受信場所で、リモートの LOB サーバーからの接続をリッスンするように続行します。 これは、下位互換性のある既定のオプションです。<br/><br/>既定値は Remote です。| 
    |**接続名**|入力**1Way**です。|  
    |**ホスト名**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>入力**localhost**です。|  
    |**ローカルのホスト名**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはローカルの IP アドレスを入力[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]です。 入力することも**localhost**です。|  
    |**[ポート]**|特定[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]と以前のバージョン。 <br/><br/>既定値は**11000**です。|  
    |**ローカル ポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>LocalHost 接続の TCP ポート番号を入力します。 場合にのみ適用**によって接続が開始される**は**リモート**です。 <br/><br/>既定値は**11000**です。|
    |**リモート ホスト**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>DNS 名またはリモートの LOB サーバーの IP アドレスを入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。|  
    |**リモートのポート**|始まる新しい[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]です。 <br/><br/>リモート ホスト接続への TCP ポート番号を入力します。 場合に適用**によって接続が開始される**に設定されている**ローカル**です。|  

9. 設定、**受信ハンドラー**に**BizTalkServerApplication**です。  
  
10. 設定、**受信パイプライン**に**BTAHL72XPipelines.BTAHL72XReceivePipeline**です。  
  
11. **[OK]** を選択して変更を保存します。  
  
12. 右クリックして、作成した受信場所を有効にし、**を有効にする**です。  

## <a name="next-step"></a>次の手順  
[手順 5: ファイル アダプタを使用して、ADT システムに受信確認を配信する送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)