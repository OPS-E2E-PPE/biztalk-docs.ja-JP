---
title: サンプル BTARN ビジネス ポリシー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db932c17-8e8f-4f7a-b165-d1d7d749cdb6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c85cbb7894f0d8bd1b61b7e7856865b49fd33859
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960624"
---
# <a name="sample-btarn-business-policy"></a>サンプル BTARN ビジネス ポリシー
このサンプルは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ビジネス ルール ポリシーに関連する XML コードです。  
  
 サンプル ファイル samplebtarnpolicy.xml は\<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\PIPAutomation\3A4 です。  
  
## <a name="demonstrates"></a>使用例  
 このコードは、次のルールを含んでいるビジネス ルール ポリシーを示します。  
  
 IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message  
  
## <a name="see-also"></a>参照  
 [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)