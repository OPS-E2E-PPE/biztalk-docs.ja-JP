---
title: 手順 2:Contoso 取引先組織の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating partner organizations
ms.assetid: ebb3b166-3781-40b9-89d4-2ca0c83d05f3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d540a24be7ae5421956a3ad80536490f5a9fef6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281285"
---
# <a name="step-2-creating-the-contoso-partner-organization"></a>手順 2:Contoso 取引先組織の作成
この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール、新しい取引を作成します。 このチュートリアルでは、取引先パートナーは、Contoso 組織です。  

### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを開始するには  

- クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。  

### <a name="to-create-fabrikam-as-a-trading-partner"></a>取引先パートナーとして Fabrikam を作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**パートナー**、 をポイント**新規**、 をクリックし、**パートナー**.  

2. 新しいパートナーのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います<strong>:</strong>  


   |          プロパティ          |                             目的                              |
   |----------------------------|---------------------------------------------------------------------|
   |          **名前**          |                          型**CONTOSO**します。                          |
   |          **GBI**           |                         型**123456789**します。                         |
   | **パートナーの分類** |          選択**製造元**ドロップダウン リストから。           |
   | **証明書の署名**  | 選択**Contoso Signature [Thumbprint]** ドロップダウン リストから。  |
   | **暗号化証明書** | 選択**Contoso Encryption [Thumbprint]** ドロップダウン リストから。 |


3. をクリックして、**連絡先プロパティ**タブをクリックし、次の操作を行います。  


   |       プロパティ        |               目的                |
   |-----------------------|-----------------------------------------|
   |   **連絡先の名前**    |           型**John Doe**します。            |
   |  **E-mail Address**   | 型 <strong>jdoe@contoso.com</strong>します。 |
   | **電話番号**  |         型**555-555-5555**します。          |
   |    **Fax 番号**     |         型**555-555-5555**します。          |
   | **サプライ チェーン コード** |     型**電子部品**します。     |


4. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [ステップ 3:Fabrikam 0C2 取引先契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)