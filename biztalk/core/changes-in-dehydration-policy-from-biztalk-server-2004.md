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
ms.openlocfilehash: 9daf93fd6c925e5412aef3f4e985dd966f576eee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>BizTalk Server 2004 からの退避ポリシーの変更点
BizTalk Server の退避ポリシーは、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] に変更されています。 [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] と [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の違いに関する説明は、[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] で退避を判断する次のブール値 (true = 退避) に集約されます。  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 退避ポリシー[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]マイナーこの方法で変更されました。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]2 よりも長く待機がある場合、受信/遅延/待ち受けで常に退避 ***MaxThreshold**です。