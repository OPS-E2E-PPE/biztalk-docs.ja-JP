---
title: BAM によるビジネス プロセス管理ソリューションの監視 |Microsoft Docs
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
ms.openlocfilehash: 3c46c52dad2352f0aea2d0d69af477458ed59ba5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324556"
---
# <a name="monitoring-the-business-process-management-solution-with-bam"></a>BAM によるビジネス プロセス管理ソリューションの監視
ソリューションは、ビジネス アクティビティ監視 (BAM) API を使用して注文の処理手順を監視します。 ビジネス プロセスの設計では、複数のステージでは、アクティビティを分割します。 を通じて、アクティビティを継続的なプロセスの作成を再び組み合わせて指定できます。 BAM では、時間別のバックエンドが使用すると、注文の数は、完了、およびその他の同様の情報をされていることがわかるように、集計データも提供します。  
  
 サービス指向ソリューションのようには、新しい**OrchestrationEventStream**オブジェクト。 詳細については、 **OrchestrationEventStream**オブジェクト、」何が「OrchestrationEventStream オブジェクト「を参照してください[BAM を使用したサービス指向ソリューションの監視](../core/monitoring-the-service-oriented-solution-with-bam.md)します。  
  
 BAM の詳細については、次を参照してください。[ビジネス アクティビティの監視を使用して](../core/using-business-activity-monitoring.md)します。 追跡プロファイル エディター (TPE) についての情報を参照してください。[追跡プロファイル エディター](../core/tracking-profile-editor.md)します。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>OrchestrationEventStream オブジェクトのラップ  
 ビジネス プロセス管理ソリューションをラップする、サービス指向ソリューションと同様、 **OrchestrationEventStream**オブジェクト。 また、サービス指向ソリューションのようにすべてのメソッドは静的あるため、オーケストレーションは、メソッドを使用するにはオブジェクトのインスタンスを作成する必要はありません。 つまりも追跡で使用されるオブジェクトがシリアル化する必要はありませんし、保存する必要はありません (シリアル化可能にする必要は) 場合は、エンジンによってオーケストレーションが退避します。 ただし、ビジネス プロセス管理ソリューションがラップ**OrchestrationEventStream**いくつかのオブジェクト、1 つから派生したもの、オブジェクト抽象化します。  
  
 抽象クラスは**BasicActivity**します。 抽象ですが、クラスを派生クラスのテンプレートとして実際に処理しません。 代わりに、その静的メソッドでは、を通じて、派生クラス内で修飾なしのメソッドのセットを提供します。 これを実際には、により、メソッドの 4 つの既定の実装。 4 つの静的メソッドは次のとおりです。**CreateActivityId**、 **BeginActivity**、 **UpdateActivity**、および**EndActivity**します。  
  
 クラスのオーバー ロード、 **BeginActivity**メソッド。 別のバージョンは 1 つの引数として、アクティビティ名を受け取り、アクティビティの識別子として使用する GUID を作成を受け取り、アクティビティ名とアクティビティ識別子、アクティビティの識別子を取得し、それ自体のバージョンを呼び出します。 この引数を 1 つのバージョンでは、注文可能性があります、一意識別子がない場合に役立ちます。  
  
 **CreateActivityId**メソッドは文字列と要求識別子などの一意の識別子と、アンダー スコアで連結する文字列を返します。 これは、一意のアクティビティ識別子を提供しは、派生クラスで広く使用します。 **BeginActivity**、 **UpdateActivity**、および**EndActivity**メソッドを呼び出す、 **BeginActiviy**、 **UpdateActivity**、および**EndActivity**メソッドの**OrchestrationEventStream**します。  
  
 ソリューションからのクラスを派生する**BasicActivity** 、注文ブローカ (**CustomerOrderRequest**)、注文マネージャ (**OrderManager**)、および処理ステージ (**ServiceOrderRequest**)。 各クラスは、アクティビティに対応します。 各クラスで使用されるアクティビティ名の文字列を提供する**CreateActivityId**識別子と同様の方法でアクティビティ マイルス トーンの特化、アクティビティを作成します。  
  
 注文ブローカが注文を渡し、後で応答を受信するため、注文の要求識別子に指定されたアクティビティ識別子を回復する方法が含まれています。 これにより、注文の処理の最後の要素の追跡を続けるビジネス プロセスです。  
  
> [!NOTE]
>  顧客サービスの web アプリケーションではなく、ファイル機能からの注文を送信する場合は、要求ごとに一意の識別子を追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [ビジネス プロセス管理ソリューションの開発](../core/developing-a-business-process-management-solution.md)