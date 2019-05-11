---
title: 手順 2:パートナー組織の作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- partner organization
- trading partners, partner organization
- loopback tutorial, creating partner organization
ms.assetid: 489bc961-dcb6-4610-989d-c06ba9f71b02
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 351a95b2d3f507b525e1315a5d9d1b5733953ee5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281195"
---
# <a name="step-2-create-the-partner-organization"></a>手順 2:パートナー組織を作成します。
この手順で、Microsoft® を使用して、パートナー組織を作成する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。  

### <a name="to-create-the-partner-organization"></a>取引先組織を作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン\>Accelerator for RosettaNet**、右クリックして**パートナー**、をクリックして**新規**、 をクリックし、**パートナー**します。  

2. **新しいパートナーのプロパティ** ダイアログ ボックスで、次の操作を行います。  


   | プロパティ |     目的      |
   |----------|---------------------|
   | **名前** |  型**パートナー**します。  |
   | **GBI**  | 型**987654321**します。 |


3. **新しいパートナーのプロパティ** ダイアログ ボックスで、**連絡先プロパティ** タブで、次の操作を行います。  


   |       プロパティ        |                目的                |
   |-----------------------|------------------------------------------|
   |   **連絡先の名前**    |            型**Jane Doe**します。            |
   |  **E-mail Address**   | 型 <strong>jdoe@fabrikam.com</strong>します。 |
   | **電話番号**  |          型**555-555-5555**します。          |
   |    **Fax 番号**     |          型**555-555-5555**します。          |
   | **サプライ チェーン コード** |     型**電子部品**します。      |


4. をクリックして**適用**、し**OK**します。  

> [!NOTE]
>  暗号化証明書がある場合は、ここで構成します。 暗号化証明書を構成する方法の詳細については、次を参照してください。[証明書の管理](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)します。  

## <a name="see-also"></a>参照  
 [ステップ 3:PIP (Partner Interface Process) の編集](../../adapters-and-accelerators/accelerator-rosettanet/step-3-edit-the-partner-interface-process.md)