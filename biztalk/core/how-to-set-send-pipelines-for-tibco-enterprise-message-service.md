---
title: "TIBCO Enterprise Message Service のパイプラインを送信を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- setting send pipelines
- pipelines, send
ms.assetid: 6a84d874-4b4d-4b23-913f-f5c72af1e96e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d037782e2580d52c6609c3669e2805aae92ce9eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a>TIBCO Enterprise Message Service 用の送信パイプラインを設定する方法
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service では、送信パイプラインに XMLTransmit、受信パイプラインに XMLReceive をそれぞれ選択する必要があります。  
  
### <a name="to-set-pipelines"></a>パイプラインを設定するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO EMS**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
4.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [設定する方法 TIBCO Enterprise Message Service 用の受信パイプライン](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)