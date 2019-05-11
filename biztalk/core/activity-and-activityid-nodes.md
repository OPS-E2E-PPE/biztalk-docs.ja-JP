---
title: アクティビティ ノードと ActivityID ノード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ad89c82f7eac4aca14ca3d424a5bda6056f95f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361818"
---
# <a name="activity-and-activityid-nodes"></a>アクティビティ ノードと ActivityID ノード
アクティビティ ノードと ActivityID ノードは、アクティビティ定義の格納と識別に使用します。 アクティビティ ノードは、アクティビティ定義に含まれる項目の親フォルダーです。 すべてのデータ項目とビジネス イベント ノードは、関連付けられているアクティビティ ノードの下位ノードで、アクティビティ ノードに含まれています。 アクティビティ ノードの名前は、アクティビティ自体の名前が反映されます。  
  
 ActivityID ノードは、アクティビティ定義で自動的に生成される項目で、アクティビティの一意な識別子を保持することを目的としています。 ActivityID ノードは、ユーザーが指定した識別子またはシステムによって生成された識別子を追跡する場合に使用できます。 たとえば、システムで注文番号を一意な識別子として保持している場合、注文番号を ActivityID として使用することができます。この場合、ActivityID の値は、注文書のスキーマに含まれる PO 番号フィールドなどのイベント ソースからマップすることになります。 ただし、注文番号の値が一意な識別子ではない場合は、ノードに値をマップする必要はありません。ノードに値をマップしないと、BAM により、実行時に一意な識別子が自動的に生成されます。  
  
 アクティビティは他のアクティビティに関連付けることができます。 一部のシナリオでは、このようなリレーションシップは明示的に監視モデルの一部となります。  具体的には、ユーザー ビューに 2 つ以上のアクティビティが含まれている場合、これらのアクティビティ間にはリレーションシップが自動的に作成されます。  このようなリレーションシップが存在する場合、既知のピア アクティビティごとに、アクティビティ ツリーのアクティビティ ノードの下にリレーションシップ ノードが自動的に作成されます。 データ リレーションシップが存在し、それらのデータが展開されるビューが存在しない場合は、アクティビティ ツリーにリレーションシップ ノードを手動で追加することができます。  
  
 どちらの場合も、リレーションシップ ノードは、関連するアクティビティの識別子を提供することを目的としています。 たとえば、発注と出荷の間には多対多のリレーションシップが存在することがあります (1 つの PO に複数回の出荷で対応したり、1 回の出荷が複数の PO の製品に対応することがあります)。  各発注アクティビティ レコードが複数の関連する出荷に対するポインターを持ったり、各出荷アクティビティ レコードが 1 つ以上の発注に対してポインターを持ったりすることがあります。  データベースの観点では、リレーションシップ ノードの値は、他のアクティビティのテーブルに対する外部キーになります。  
  
## <a name="working-with-activity-id-nodes"></a>ActivityID ノードの操作  
 たとえば、次のシナリオ: EquityLoan オーケストレーションに LoanProcess アクティビティ フォルダーが含まれています。 このオーケストレーションで次のビジネス イベントを参照しているとします。  
  
- LoanApplicationReceived  
  
- CHRequest  
  
- CHResponse  
  
- AppraisalRequest  
  
- AppraisalResponse  
  
- 承認  
  
- 拒否  
  
  ソリューション開発者は ActivityID ノードを使用して、アクティビティを一意に識別するデータ (注文番号など) を抽出できます。サンプル シナリオでは、メッセージの SSN フィールドのデータを抽出しました。 データを ActivityID ノードにドラッグしない場合、ビジネス アクティビティは、自動的に生成された GUID により識別されます。  
  
  異なるオーケストレーションに含まれているビジネス イベントまたはマイルストーンの間でリレーションシップを定義するには、ターゲット オーケストレーションで ActivityID を参照する必要があります。 TPE を使用してリレーションシップを実装する方法の詳細については、次を参照してください。[リレーションシップ ノード](../core/relationship-nodes.md)します。  
  
## <a name="see-also"></a>参照  
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)