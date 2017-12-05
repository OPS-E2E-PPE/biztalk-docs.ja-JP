---
title: "BizTalk Server 2004 からの退避ポリシーの変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c760bffe-5f64-4eb2-bc23-89d7c9310f39
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167c53d953369d7b35138995b4f38ad8994c18cb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>BizTalk Server 2004 からの退避ポリシーの変更点
BizTalk Server の退避ポリシーが変更された[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]BizTalk Server にします。 違いの説明は、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]で退避を判断するブール値を次で BizTalk Server をまとめると[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)](true = 退避)  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 BizTalk Server の退避ポリシーは、このマイナーの方法で変更されました。 BizTalk Server、常に退避受信/遅延/待ち受けで 2 よりも長く待機している場合 ***MaxThreshold**です。