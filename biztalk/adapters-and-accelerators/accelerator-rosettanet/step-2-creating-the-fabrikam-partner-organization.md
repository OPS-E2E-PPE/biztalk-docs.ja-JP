---
title: '手順 2: Fabrikam パートナー組織の作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5634b1394a7c390dfddbcf3b893e2496e20a08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004363"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a>手順 2: Fabrikam パートナー組織の作成
この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール、新しい取引を作成します。 このチュートリアルでは、Fabrikam 組織という取引先を使用します。  

### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  

- Contoso コンピューターでは、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**。、 をクリックし、 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。  

### <a name="to-create-fabrikam-as-a-trading-partner"></a>Fabrikam という名前の取引先を作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、 をクリックし、**パートナー**.  

2. 新しいパートナーのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います<strong>:</strong>  


   |          プロパティ          |                                                                              目的                                                                               |
   |----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |          **名前**          |                                                                          型**FABRIKAM**します。                                                                           |
   |          **GBI**           | 型**987654321**します。 **注:** を同じコンピューターで、Loopback チュートリアルを実行する gbi には異なる 987654321 以外の値を入力する必要があります。 |
   | **パートナーの分類** |                                                              選択**買い物客**ドロップダウン リストから。                                                              |
   | **証明書の署名**  |                                                  選択**Fabrikam Signature [Thumbprint]** ドロップダウン リストから。                                                  |
   | **暗号化証明書** |                                                 選択**Fabrikam Encryption [Thumbprint]** ドロップダウン リストから。                                                  |


3. をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。  


   |       プロパティ        |                目的                |
   |-----------------------|------------------------------------------|
   |   **連絡先の名前**    |            型**Jane Doe**します。            |
   |  **E-mail Address**   | 型 <strong>jdoe@fabrikam.com</strong>します。 |
   | **電話番号**  |          型**555-555-5555**します。          |
   |    **Fax 番号**     |          型**555-555-5555**します。          |
   | **サプライ チェーン コード** |     型**電子部品**します。      |


4. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [手順 3: Contoso 0C2 取引先契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)