---
title: "オーケストレーションを開発するためのセキュリティに関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-developing-orchestrations"></a>オーケストレーションを開発するためのセキュリティに関する考慮事項
オーケストレーションを設計する際は、潜在的なセキュリティの問題を考慮する必要があります。  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a>信頼されないメッセージのコンテンツに基づくサブスクリプションを防ぐ  
 メッセージのコンテンツやコンテキストに基づいてサブスクリプションを作成する可能性のあるオーケストレーション インスタンスが、権限レベルの低いメッセージによって開始されないようにするため、信頼されないメッセージのコンテンツやコンテキストに基づくメッセージのサブスクリプションが、オーケストレーションで作成されないようにすることを強くお勧めします。  
  
 セキュリティの詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のセキュリティで保護する](../core/securing-biztalk-server.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの作成](../core/creating-orchestrations.md)   
 [オーケストレーションについて](../core/about-orchestrations.md)