---
title: ロール リンクとサービス リンク ロール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7b52a13878363e79b9b2ffa3e600de16aeacd3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254716"
---
# <a name="role-links-and-service-link-roles"></a>ロール リンクとサービス リンク ロール
A*ロール*またはサービスを使用して、サービスを実装するポートの種類のコレクションです。 ロールは、パーティは、1 つまたは複数のオーケストレーションを持つことができますの対話の種類を表します。 ロールは、柔軟性とパーティの増加の数と管理の容易さを提供します。 たとえば、オーケストレーションは、出荷業者のロールを使用する場合があります。 出荷業者は、1 つまたは 2 つのパーティが関連付けられている必要があります。 オーケストレーションは、使用して商品の出荷業者を決定したら、出荷業者ロールのパーティの価格を比較します。  
  
 A*ロール リンクの種類*は、2 つのサービスやオーケストレーション間のリレーションシップを表すプロパティです。 リレーションシップ内のサービスの各部分を定義し、各ロールで提供されるポートの種類を指定します。  
  
 パーティ、または組織単位、オーケストレーションと連携する BizTalk Server 外部のエンティティを表します。 BizTalk Server では、メッセージを交換する各組織は、パーティによって表されます。 パーティがロールに参加させてと連携する方法を定義できます。  
  
 デプロイまたはオーケストレーションに関連付けられているときに、ロール リンクの種類を削除できます。  
  
## <a name="orchestrations-and-roles"></a>オーケストレーションとロール  
 ロール リンクの種類を使用するオーケストレーションを展開するときに、ロールが構成データベースに保存します。 ロールは、1 つ以上のオーケストレーションで使用できる、ので、管理データベースは、ロール リンクの種類の 1 つだけコピーを保存します。  
  
 BizTalk プロジェクトに同じ名前および名前空間を持つ個別のオーケストレーション (.odx) ファイルで 2 つのロール リンクの種類が含まれている場合、BizTalk プロジェクトはコンパイルされません。  
  
### <a name="orchestration-removals-that-use-roles"></a>ロールを使用してオーケストレーションの削除  
 ロールを使用するオーケストレーションを含むアセンブリを展開解除すると、ロール リンクの種類を 1 つ以上のオーケストレーションで使用できる、ため、管理データベースは、他のオーケストレーションが、ロールを使用していない場合にのみ、ロールを削除します。  
  
 さらに、それに参加しているパーティがない場合にのみ、管理データベースは、ロールを削除します。 それに参加しているパーティを持つロールを上書きすることはできず、同様、それに参加しているパーティを持つロールを削除できません。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md)   
 [アイテム](../core/artifacts.md)