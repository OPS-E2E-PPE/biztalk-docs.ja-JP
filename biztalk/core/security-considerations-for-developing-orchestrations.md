---
title: オーケストレーションを開発するためのセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d159a96052871796c102dc628dae2a06d85046
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280320"
---
# <a name="security-considerations-for-developing-orchestrations"></a>オーケストレーションを開発するためのセキュリティに関する考慮事項
オーケストレーションを設計するときは、潜在的なセキュリティの問題を検討してください。  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a>信頼されていないメッセージのコンテンツに基づいてサブスクリプションを回避します。  
 特権の低いメッセージがメッセージのコンテンツやコンテキストに基づいてサブスクリプションを作成する可能性のあるオーケストレーション インスタンスを開始していないことを確認するを強くお勧め、オーケストレーションがメッセージのサブスクリプションを作成できません。コンテンツや信頼されていないメッセージのコンテキストに基づいています。  
  
 セキュリティについて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[BizTalk Server のセキュリティで保護する](../core/securing-biztalk-server.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの作成](../core/creating-orchestrations.md)   
 [オーケストレーションについて](../core/about-orchestrations.md)