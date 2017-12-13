---
title: "手順 2: Fabrikam パートナー組織の作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de00977edecb97420742a6510c3290cfe3c76ea5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a>手順 2: Fabrikam パートナー組織の作成
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して新しい取引先を作成します。 このチュートリアルでは、Fabrikam 組織という取引先を使用します。  
  
### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  
  
-   Contoso のコンピューターでをクリックして**開始**、指す**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**、クリックして **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a>Fabrikam という名前の取引先を作成するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、クリックして**パートナー**.  
  
2.  新しいパートナーのプロパティ ダイアログ ボックスで、**全般** タブで、次の操作、**:**  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**FABRIKAM**です。|  
    |**[GBI]**|型**987654321**です。 **注:**を同じコンピューターでループバック チュートリアルを実行する場合は、異なる 987654321 以外は、[gbi] に値を入力する必要があります。|  
    |**パートナーの分類**|選択**Shopper**ドロップダウン リストからです。|  
    |**署名証明書**|選択**Fabrikam Signature [Thumbprint]**ドロップダウン リストからです。|  
    |**暗号化証明書**|選択**Fabrikam Encryption [Thumbprint]**ドロップダウン リストからです。|  
  
3.  クリックして、**連絡先のプロパティ**タブをクリックし、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**連絡先の名前**|型**Jane Doe**です。|  
    |**E-mail Address**|型 **jdoe@fabrikam.com**です。|  
    |**電話番号**|型**555-555-5555**です。|  
    |**Fax 番号**|型**555-555-5555**です。|  
    |**サプライ チェーン コード**|型**電子部品**です。|  
  
4.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [手順 3: Contoso 0C2 取引先契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)