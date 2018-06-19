---
title: '手順 5: Contoso 3 a 2 取引を作成するパートナーの契約 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: 5c602c9c-22bd-450f-bb14-6848b1414c03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624cd67b5a8b07cadcddb52efecafc032882f840
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964712"
---
# <a name="step-5-creating-the-contoso-3a2-trading-partner-agreement"></a>手順 5: Contoso 3 a 2 取引先アグリーメントの作成
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。 3A2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。  
  
### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  
  
-   をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。  
  
### <a name="to-create-the-3a2-trading-partner-agreement"></a>3A2 取引先アグリーメントを作成するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をポイント**新規**、クリックして**アグリーメント**.  
  
2.  **新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Fabrikam_To_Contoso_3A2**です。|  
    |**プロセスの構成**|選択**STD_3A2_R02.00.00A**ドロップダウン リストからです。|  
    |**自分の所属組織**|選択**Contoso**ドロップダウン リストからです。|  
    |**パートナー組織**|選択**Fabrikam**ドロップダウン リストからです。|  
    |**RNIF のバージョン**|選択 **[v02.00.01]** ドロップダウン リストからです。|  
    |**ホーム ロール**|選択**Product Supplier (応答側)** ドロップダウン リストからです。|  
    |**使用方法**|選択**テスト**ドロップダウン リストからです。|  
  
3.  クリックして、**ポート**タブをクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクションの URL**|型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**シグナル URL**|型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
    |**同期 URL**|型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**|  
  
4.  **[OK]** をクリックします。  
  
5.  右クリックし、 **Fabrikam_To_Contoso_3A2**アグリーメント、およびクリック**Activate**です。  
  
## <a name="see-also"></a>参照  
 [手順 6: Contoso 3A4 取引先契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)