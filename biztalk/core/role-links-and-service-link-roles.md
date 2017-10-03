---
title: "ロール リンクとサービス リンク ロール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6630b1ad22ba86f3efe8a19409f3b731880c8a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="role-links-and-service-link-roles"></a>ロール リンクとサービス リンク ロール
A*ロール*サービスを使用するか、サービスを実装するポートの種類のコレクションです。 ロールは、パーティが単一または複数のオーケストレーションを持つ場合の対話処理の種類を表します。 パーティの数が増えるにつれて、ロールによって管理を柔軟かつ簡単に行えるようになります。 たとえば、あるオーケストレーションで出荷業者のロールを使用するとします。 出荷業者は、1 つまたは 2 つのパーティが関連付けられている必要があります。 オーケストレーションでアイテムの出荷業者を決定する際には、出荷業者ロールのパーティの価格が比較されます。  
  
 A*ロール リンクの種類*は、2 つのサービスやオーケストレーション間のリレーションシップを表すプロパティです。 関係にかかわる各サービスが受け持つ役割を定義し、各ロールから提供されるポートの種類を指定します。  
  
 パーティ (つまり、組織単位) は、オーケストレーションと連携する BizTalk Server 外部のエンティティを表します。 BizTalk Server では、メッセージ交換の対象となる各組織は、パーティで表されます。 パーティをロールに参加させてパーティと連携する方法を定義できます。  
  
 ロール リンクの種類がオーケストレーションに関連付けられている場合、ロール リンクの種類を展開または削除できます。  
  
## <a name="orchestrations-and-roles"></a>オーケストレーションとロール  
 ロール リンクの種類を使用するオーケストレーションを展開すると、構成データベースがロールを保存します。 複数のオーケストレーションでロールを使用できるため、管理データベースは、ロール リンクの種類を 1 つだけ保存します。  
  
 同じ名前および名前空間を持つ個別のオーケストレーション (.odx) ファイルに 2 つのロール リンクの種類を含む BizTalk プロジェクトを使用している場合、BizTalk プロジェクトはコンパイル処理を行いません。  
  
### <a name="orchestration-removals-that-use-roles"></a>ロールを使用するオーケストレーションの削除  
 複数のオーケストレーションでロール リンクの種類を使用できるため、ロールを使用するオーケストレーションを含むアセンブリを展開解除すると、管理データベースは、該当するロールを使用しているオーケストレーションがない場合にそのロールだけを削除します。  
  
 また、管理データベースは、参加しているパーティがない場合、ロールだけを削除します。 参加しているパーティを持つロールを上書きできないのと同様に、参加しているパーティを持つロールは削除もできません。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでロール リンクの使用](../core/using-role-links-in-orchestrations.md)   
 [成果物](../core/artifacts.md)