---
title: BAM によるビジネス プロセス管理ソリューションの監視 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, monitoring
- monitoring, process management solutions
ms.assetid: 7c5fde9d-6eef-41c9-979c-ac7e5a172812
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26a8b795b90b75518f6c1ec21a6ca6d8f0f0d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264370"
---
# <a name="monitoring-the-business-process-management-solution-with-bam"></a>BAM によるビジネス プロセス管理ソリューションの監視
このソリューションは、ビジネス アクティビティ監視 (BAM) API を使用して、注文の処理順序を監視します。 ビジネス プロセスのデザインでは、アクティビティを複数のステージに分けます。 アクティビティを再び組み合わせて、連続するプロセスのような一体感を持たせることができます。 BAM は集計データも提供するので、各バックエンドに要する時間、完了した注文数、その他の関連情報を入手できます。  
  
 サービス指向ソリューションと同様に使用して、新しい**OrchestrationEventStream**オブジェクト。 については、 **OrchestrationEventStream**オブジェクト」新機能は、「OrchestrationEventStream オブジェクト「を参照してください[BAM を使用するサービス指向ソリューションの監視](../core/monitoring-the-service-oriented-solution-with-bam.md)です。  
  
 BAM の詳細については、次を参照してください。[を使用したビジネス アクティビティ監視](../core/using-business-activity-monitoring.md)です。 追跡プロファイル エディター (TPE) についての詳細について、次を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)です。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトのラップ処理  
 ビジネス プロセス管理ソリューションがラップ、サービス指向ソリューションと同様に、 **OrchestrationEventStream**オブジェクト。 また、サービス指向ソリューションと同様に、メソッドはすべて静的であるため、メソッドを使用するためにオーケストレーションでオブジェクトのインスタンスを作成する必要はありません。 つまり、エンジンによってオーケストレーションが退避される場合は、追跡に使用したオブジェクトをシリアル化する必要がなく、保存する (シリアル化可能にする) 必要もありません。 ただし、ビジネス プロセス管理ソリューションをラップ**OrchestrationEventStream**いくつか、オブジェクトと 1 つのすべての派生オブジェクトを抽象化します。  
  
 抽象クラスは**BasicActivity**です。 このクラスは抽象ですが、派生したクラスのテンプレートとして機能するというよりは、 クラスの静的メソッドを経由して、派生したクラス内で修飾なしで使用できる一連のメソッドを提供します。 このため、メソッドの既定の実装は 4 種類用意されています。 次の 4 つの静的メソッドは、: **CreateActivityId**、 **BeginActivity**、 **UpdateActivity**、および**EndActivity**です。  
  
 クラスのオーバー ロード、 **BeginActivity**メソッドです。 このメソッドには、アクティビティ名を唯一の引数として受け取り、GUID を作成してアクティビティ識別子として使用するバージョンがあります。このバージョンは、同じメソッドの別のバージョン (アクティビティ名とアクティビティ識別子を受け取るバージョン) を呼び出して、アクティビティ識別子を返します。 この引数を 1 つだけ受け取るバージョンは、注文に一意の識別子がない場合に役立ちます。  
  
 **CreateActivityId**メソッド (string) と要求識別子などの一意の識別子を受け取り、アンダー スコアで連結する文字列を返します。 これは一意のアクティビティ識別子となり、派生したクラスで広く使用されます。 **BeginActivity**、 **UpdateActivity**、および**EndActivity**メソッドの呼び出し、 **BeginActiviy**、 **UpdateActivity**、および**EndActivity**のメソッド**OrchestrationEventStream**です。  
  
 ソリューションからのクラスを派生する**BasicActivity**注文ブローカの (**CustomerOrderRequest**)、注文マネージャ (**OrderManager**)、および処理ステージ (**ServiceOrderRequest**)。 クラスはそれぞれ、アクティビティに対応しています。 各クラスで使用するアクティビティの名前の文字列の提供**CreateActivityId**活動を作成するメソッドと同様に識別子に特化したアクティビティ マイルス トーンです。  
  
 注文ブローカは注文を渡し、後で応答を受け取るため、注文の要求識別子に割り当てられたアクティビティ識別子を回復するメソッドを含んでいます。 これによって、ビジネス プロセスが注文処理の最終的な要素の追跡を続けることが可能になります。  
  
> [!NOTE]
>  カスタマ サービス Web アプリケーションを使用せずに、ファイル機能から注文を送信した場合は、要求ごとに一意の識別子を追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)