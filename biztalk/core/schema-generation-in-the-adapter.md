---
title: "アダプターではスキーマの生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, generating
- writing, schemas
ms.assetid: 43b69383-bae0-401b-9620-d4302db799b2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d10d927e4ede59e716b3f9838c96bac8cd144a81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="schema-generation-in-the-adapter"></a>アダプタでのスキーマの生成
TIBCO Rendezvous システムには、メッセージの種類のリポジトリは含まれていません。 すべてのメッセージの構築と解析は、Rendezvous アプリケーション レベルに組み込まれています。 この制限により、Microsoft BizTalk Adapter for TIBCO Rendezvous ではスキーマ生成機能を利用できません。  
  
## <a name="writing-schemas"></a>スキーマの記述  
 スキーマを記述して、使用する必要があります**既存項目の追加**オーケストレーションで使用できるは、インポートする Visual Studio でします。 スキーマは、BizTalk Server の開発ツールに必要で、Visual Studio での統合において非常に重要な役割を果たします。 BizTalk Server の開発者は、完全なスキーマを作成する必要はなく、最小限のスキーマやその中間のスキーマも作成できます。  
  
## <a name="see-also"></a>参照  
 [作業の開始](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)