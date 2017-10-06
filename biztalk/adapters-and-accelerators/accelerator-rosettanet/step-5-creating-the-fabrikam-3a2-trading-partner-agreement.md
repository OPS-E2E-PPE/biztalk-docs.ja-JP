---
title: "手順 5: Fabrikam 3 a 2 取引を作成するパートナーの契約 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: a5fafdc6-e9dd-4d15-98a2-8b603901308c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e945223013e80c4f0550a388cbc0811861846ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a>手順 5: Fabrikam 3 a 2 取引先アグリーメントの作成
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。 3A2 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。  
  
### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  
  
-   をクリックして**開始**、をポイント**すべてのプログラム**、をポイント**Microsoft BizTalk\<バージョン > Accelerator for RosettaNet**、クリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。  
  
### <a name="to-create-the-3a2-trading-partner-agreement"></a>3A2 取引先アグリーメントを作成するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、をポイント**新規**、クリックして**アグリーメント**.  
  
2.  **新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Fabrikam_To_Contoso_3A2**です。|  
    |**プロセスの構成**|選択**STD_3A2_R02.00.00A**ドロップダウン リストからです。|  
    |**自分の所属組織**|選択**Fabrikam**ドロップダウン リストからです。|  
    |**パートナー組織**|選択**Contoso**ドロップダウン リストからです。|  
    |**RNIF のバージョン**|選択**[v02.00.01]**ドロップダウン リストからです。|  
    |**ホーム ロール**|選択**Customer (開始側)**ドロップダウン リストからです。|  
    |**使用方法**|選択**テスト**ドロップダウン リストからです。|  
  
3.  クリックして、**ポート**タブをクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクションの URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
    |**シグナル URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
    |**同期 URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
  
4.  **[OK]**をクリックします。  
  
5.  右クリックし、 **Fabrikam_To_Contoso_3A2**アグリーメントをクリックして**Activate**です。  
  
## <a name="see-also"></a>参照  
 [手順 6: Fabrikam 3A4 取引先アグリーメントの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)