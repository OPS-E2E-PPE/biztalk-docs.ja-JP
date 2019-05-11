---
title: 手順 1:Contoso ホーム組織の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating home organizations
- creating, home organizations
- home organizations, creating
ms.assetid: 0e7a53b9-ae59-4cd1-88bd-0ada7e65acba
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3893d582a85708190f1f030b06187fcd8f152bd6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281596"
---
# <a name="step-1-creating-the-contoso-home-organization"></a>手順 1:Contoso ホーム組織の作成
この手順で、Microsoft® を使用して[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Contoso ホーム組織を作成する管理コンソール。  

### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを開始するには  

- Contoso コンピューターでは、次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**。し**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。  

### <a name="to-create-the-home-organization"></a>ホーム組織を作成するには  

1. [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**ホーム組織**、 をポイント**新規**、順にクリックします**ホーム組織**します。  

2. 新しいホーム組織のプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います。  


   |               プロパティ               |                                                                              目的                                                                               |
   |--------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |               **名前**               |                                                                           型**CONTOSO**します。                                                                           |
   |               **GBI**                | 型**123456789**します。 **注:** 同じコンピューターで、Loopback チュートリアルを実行した場合の gbi に 123456789 以外の異なる値を入力する必要があります。 |
   | **ホーム組織の分類** |                                                           選択**製造元**ドロップダウン リストから。                                                            |


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
 [手順 2:Fabrikam 取引先組織の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-the-fabrikam-partner-organization.md)