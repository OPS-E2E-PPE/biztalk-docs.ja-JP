---
title: "TIBCO Rendezvous の送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>TIBCO Rendezvous の送信ポートを作成する方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成するには、次の手順を実行します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。  
  
2.  右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。  
  
3.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  たとえば、送信ポートの名前を入力`SendToTIBCORV`です。  
  
    2.  **型**ドロップダウン リストで、 **TIBCO Rendezvous**です。  
  
    3.  **送信ハンドラー**ドロップダウン リストで、URI を選択します。  
  
    4.  送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。  
  
    5.  **受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。  
  
    6.  をクリックして**構成**送信ポートを構成します。  
  
4.  **TIBCO Rendezvous トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    1.  プロパティを入力します。  
  
         ログオン情報を設定する必要はありません。  
  
    2.  一覧で、TIBCO Rendezvous システムを表すように作成した SSO 関連アプリケーションを選択します。  
  
    3.  **SSO を使用する****はい**です。  
  
    4.  **[OK]**をクリックします。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [TIBCO Rendezvous 送信ハンドラーを作成します。](../core/creating-tibco-rendezvous-send-handlers.md)