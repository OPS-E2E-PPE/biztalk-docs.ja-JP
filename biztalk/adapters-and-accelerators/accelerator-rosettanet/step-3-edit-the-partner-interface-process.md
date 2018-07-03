---
title: '手順 3: Partner Interface Process の編集 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, PIPs
- PIPs, modifying
- loopback tutorial, modifying PIPs
ms.assetid: 4d03c598-8ed4-4135-9748-ede101997fd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b5b6d2f6b0fcbf13ab521bc318eda54ece55f4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003611"
---
# <a name="step-3-edit-the-partner-interface-process"></a>手順 3: Partner Interface Process を編集します。
この手順では、Microsoft® インターネット インフォメーション サービス (IIS) で構成されているセキュリティで保護された Sockets Layer (SSL) 証明書があるない場合は、セキュリティで保護されたトランスポートを無効にするプロセス PIP (Partner Interface) の構成設定を編集します。 ループバック シナリオでは着信メッセージと送信メッセージの署名はサポートされていないため、チュートリアルを続行するには既定の設定を変更する必要があります。 STD_0C1_R01.02 PIP を変更します。  
  
### <a name="to-edit-the-std0c1r0102-pip"></a>STD_0C1_R01.02 PIP を編集するには  
  
1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン\>Accelerator for RosettaNet**、 をクリックして**プロセス構成設定**、右クリックして**STD_0C1_R01.02**、 をクリックし、**プロパティ**します。  
  
2. STD_0C1_R01.02Properties ダイアログ ボックスで、上、**アクティビティ**タブで、設定、**セキュリティで保護されたトランスポートの必要性が**オプションを`False`します。 この手順は、IIS Web サーバーに SSL 証明書がない場合にのみ実行します。  
  
3. 設定、**否認不可のために必要な**に`False`に設定して、**認証の必要性**に`False`設定**発信元とコンテンツの否認**に`False`、 をクリックし、 **OK**します。  
  
    これによって、否認不可と、メッセージに署名するための証明書の使用が無効になります。  
  
## <a name="see-also"></a>参照  
 [手順 4: 取引先アグリーメントを作成します。](../../adapters-and-accelerators/accelerator-rosettanet/step-4-create-a-trade-agreement.md)   
 [承認プロパティと否認不可プロパティ](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)