---
title: "JD Edwards EnterpriseOne 用送信ポートを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne 用送信ポートの作成方法
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用して送信ポートを作成します。  
  
### <a name="to-create-a-send-port"></a>送信ポートを作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Server**、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  BizTalk Server 管理コンソールで、次のように展開します**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、を展開**アプリケーション**、の順に展開し、。送信ポートを作成するアプリケーション。  
  
3.  右クリック**送信ポート** をクリック**新規**、クリックして**静的な送信請求-応答ポート**です。  
  
4.  **送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。  
  
    -   **名前**ボックスに、送信ポートの名前を入力 (たとえば、 `SendToJDE`)。  
  
    -   **型**ドロップダウン リストで、 **JDEdwards**です。  
  
    -   **送信ハンドラー**ドロップダウン リストで、送信ハンドラーのアドレスを選択します。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne 送信ハンドラーの作成](../core/creating-jd-edwards-enterpriseone-send-handlers.md)