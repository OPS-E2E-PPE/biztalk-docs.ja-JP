---
title: "JD Edwards EnterpriseOne の送信を設定する方法がパイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send pipelines
- send pipelines, configuring [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], configuring
- adapters [JD Edwards EnterpriseOne adapters], send pipelines
- JD Edwards EnterpriseOne adapters, configuring
ms.assetid: 4cfcecc1-febe-47c8-b75f-2b84defcdbbc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9a6337195c8050afca1f12a015ec492db7f7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne の送信パイプラインを設定する方法
Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を選択することが必要です**XMLTransmit**と**XMLReceive**の送信および受信パイプラインをそれぞれします。  
  
### <a name="to-set-pipelines"></a>パイプラインを設定するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToJDEEnterpriseOne`です。  
  
    2.  **型**ドロップダウン リストで、 **JDE EnterpriseOne**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
4.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne 送信ハンドラーの作成](../core/creating-jd-edwards-enterpriseone-send-handlers.md)