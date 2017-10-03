---
title: "手順 3: 一方向 FILE 送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ceb055f0d4d41eb82eb79cb549b082212fd1bbd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-one-way-file-send-port"></a>手順 3: 一方向 FILE 送信ポートを構成します。
このステップでは、REST インターフェイスから受信した応答メッセージを使用し、そのメッセージをファイルの場所にコピーする一方向の FILE 送信ポートを構成します。  
  
### <a name="to-configure-a-file-send-port"></a>FILE 送信ポートを構成するには  
  
1.  BizTalk Server 管理コンソールから下にある、 **BizTalk アプリケーション 1**  ノードを右クリックして**送信ポート**、 をポイント**新規**、順にクリック**静的一方向送信ポート**です。  
  
2.  [全般] タブには、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**SendPortOutAzureMarketPlaceData**です。|  
    |**型**|選択**ファイル**です。|  
    |**送信ハンドラー**|[ **BizTalkServerApplication**] を選択します。|  
    |**送信パイプライン**|選択**PassThruTransmit**です。|  
  
     をクリックして**構成**です。  
  
3.  [FILE トランスポートのプロパティ] で、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**受信フォルダー**|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が応答メッセージをコピーする場所を入力します。|  
    |**ファイル名**|保持します。`%MessageID%.xml`|  
  
4.  **フィルター**タブに書き込まれるすべてのメッセージを処理するフィルターを指定、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で作成した受信ポートでメッセージ ボックス データベース[手順 2: 双方向 Wcf-webhttp 送信ポート構成](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).  
  
    |||  
    |-|-|  
    |**プロパティ**|設定**BTS です。SPName**|  
    |**演算子**|を設定します。**==**|  
    |**値**|を設定します。`SendPortRESTAzureMarketPlace`|  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)