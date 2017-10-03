---
title: "手順 3: 編集 Partner Interface Process |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b9640f542a55d028f3df8715c49df0e9e9ad370
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-edit-the-partner-interface-process"></a>手順 3: Partner Interface Process を編集します。
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® インターネット インフォメーション サービス (IIS) に SSL (Secure Sockets Layer) 証明書が構成されていない場合に、PIP (Partner Interface Process) 構成設定を編集してセキュリティで保護されたトランスポートを無効にします。 ループバック シナリオでは着信メッセージと送信メッセージの署名はサポートされていないため、チュートリアルを続行するには既定の設定を変更する必要があります。 STD_0C1_R01.02 PIP を変更します。  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>STD_0C1_R01.02 PIP を編集するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン > Accelerator for RosettaNet**をクリックして**プロセス構成設定**を右クリックして**STD_0C1_R01.02**、クリックして**プロパティ**です。  
  
2.  STD_0C1_R01.02Properties ダイアログ ボックスで、**アクティビティ** タブで、設定、**はセキュリティで保護されたトランスポートに必要な**オプションを`False`です。 この手順は、IIS Web サーバーに SSL 証明書がない場合にのみ実行します。  
  
3.  設定、**否認不可のために必要な**に`False`設定、**承認が必要**に`False`設定、**発信元とコンテンツの否認**に`False`、クリックして**OK**です。  
  
     これによって、否認不可と、メッセージに署名するための証明書の使用が無効になります。  
  
## <a name="see-also"></a>参照  
 [手順 4: 取引先アグリーメントを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [承認と否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)