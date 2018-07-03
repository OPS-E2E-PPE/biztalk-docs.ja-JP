---
title: サンプル BTARN ビジネス ポリシー |Microsoft Docs
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
ms.openlocfilehash: 5e055d039e323fb985d9650f6f105bb3b44e9581
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974907"
---
# <a name="sample-btarn-business-policy"></a>サンプル BTARN ビジネス ポリシー
このサンプルは、Microsoft® に関連付けられている XML コード[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]ビジネス ルール ポリシー。  
  
 サンプル ファイル samplebtarnpolicy.xml は、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\PIPAutomation\3A4 します。  
  
## <a name="demonstrates"></a>使用例  
 このコードは、次のルールを含んでいるビジネス ルール ポリシーを示します。  
  
 IF (AccountNumber in the incoming 3A4 Purchase Order message = "111111111") and (MonetaryAmount of the Order < 500) THEN automatically send a response message  
  
## <a name="see-also"></a>参照  
 [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)