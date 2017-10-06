---
title: "手順 4: 取引先アグリーメントの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b94acad2b71694223b0566f86edfcfa86610099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-create-a-trade-agreement"></a>手順 4: 取引先アグリーメントを作成します。
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、ホーム組織と取引先組織間の取引アグリーメントを作成します。  
  
### <a name="to-create-a-trade-agreement"></a>取引アグリーメントを作成するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン > Accelerator for RosettaNet**を右クリックして**契約** をクリックして**新しい**、クリックして**アグリーメント**です。  
  
2.  **新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**取引アグリーメント**です。|  
    |**プロセスの構成**|選択**STD_0C1_R01.02**ドロップダウン リストからです。|  
    |**自分の所属組織**|選択**ホーム**ドロップダウン リストからです。|  
    |**パートナー組織**|選択**パートナー**ドロップダウン リストからです。|  
    |**ホーム ロール**|選択**イニシエーター**ドロップダウン リストからです。|  
  
3.  **新しいアグリーメントのプロパティ** ダイアログ ボックスで、**ポート** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクションの URL**|型**http://localhost/BTARNApp/RNIFReceive.aspx**です。|  
    |**シグナル URL**|型**http://localhost/BTARNApp/RNIFReceive.aspx**です。|  
    |**同期 URL**|空白のままにします。 同期 URL は、同期 PIP (Partner Interface Process) には必要ありません。|  
  
4.  をクリックして**適用**、順にクリック**OK**です。  
  
 取引アグリーメントを作成したら、アクティブ化する必要があります。  
  
### <a name="to-activate-the-trade-agreement"></a>取引アグリーメントをアクティブ化するには  
  
-   [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックして**契約**を右クリックして**取引先アグリーメント**をクリックして結果ペイン**Activate**.  
  
## <a name="see-also"></a>参照  
 [手順 5: ミラー アグリーメントを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)