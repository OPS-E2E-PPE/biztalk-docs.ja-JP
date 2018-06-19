---
title: 取り消し |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Retract function [Business Rules Engine], TypedData table
- Retract function [Business Rules Engine], TypedXMLDocument
- Retract function [Business Rules Engine]
- Retract function [Business Rules Engine], DataConnection
- Retract function [Business Rules Engine], .NET objects
- .NET objects
ms.assetid: 24b6b894-6810-4497-a122-8c91f0b2e816
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb4739412d310d2a69b53c8470abc7461ce3ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270114"
---
# <a name="retract"></a>取り消し
使用することができます、 **Retract**関数をビジネス ルール エンジンの作業メモリからオブジェクトを削除します。 ここでは、ルール エンジンの作業メモリからさまざまな種類のエンティティを取り消す操作に関係する動作について説明します。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 使用して、ポリシーで .NET オブジェクトが取り消され、 **Retract**関数。 この関数は、として、ビジネス ルール作成ツールで使用できる、**関数**ボキャブラリ項目: クラス (ないアセンブリまたはメソッド) にドラッグ、 **Retract**パラメーター。  
  
> [!NOTE]
>  メソッドをドラッグする場合、 **Retract**関数、エンジンは、メソッドによって返されるオブジェクトを取り消すしようとします。  
  
 .NET オブジェクトを取り消すと、ルール エンジンの作業メモリからそのオブジェクトが削除され、次に示される影響を受けます。  
  
-   述語でオブジェクトを使用しているルールでは、議題にアクションが存在する場合、議題からアクションを削除します。  
  
-   オブジェクトを使用している議題のアクションは、議題から削除されます。  
  
    > [!NOTE]
    >  前に、その他のアクションが議題によりも上位を既に実行されている可能性があります、 **Retract**関数が呼び出されました。  
  
-   オブジェクトがエンジンによって評価されなくなります。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 オリジナルを取り消すことができますか**TypedXmlDocument**をエンジンにアサートされたまたは子の 1 つを取り消す**TypedXmlDocument**の親ノードから作成された s **XmlDocument**.  
  
 例として、次の XML を使用することができますか、取り消し、 **TypedXmlDocument**順序またはの一方または両方に関連付けられている、 **TypedXmlDocument**s orderline に関連付けられています。  
  
```  
<order>  
   <orderline customer="Joe" linenumber="001">  
      <product name="router" quantity="10" cost="550" />  
   </orderline>  
   <orderline customer="Jane" linenumber="002">  
      <product name="switch" quantity="1" cost="300" />  
   </orderline>  
</order>  
```  
  
 注文オブジェクトを取り消すには、スキーマの最上位のノードを XML スキーマ ファクト ペインにドラッグします。 このノードが".xsd"で終わるし、ドキュメント ルート ノード (ドキュメント要素ノードではなく); を表します初期を表す「/」セレクターが**TypedXmlDocument**です。 ときに、親**TypedXmlDocument**が取り消される場合、すべて**TypedXmlDocument**インスタンスに関連付けられている、 **TypedXmlDocument** (すべて**TypedXmlDocument**呼び出すことによって作成された、 **Assert**関数は、ポリシーで使用されるセレクターに基づいた) 作業メモリから削除されます。  
  
 取り消すには、個々 の子のみ**TypedXmlDocument** (つまり、orderline) に XML スキーマ ペインからこのノードをドラッグすることができます、 **Retract**関数。 重要な点はすべて**TypedXmlDocument**s は最上位レベルに関連付けられた**TypedXmlDocument**を最初にアサートされたではなく、 **TypedXmlDocument**XML ツリーの階層で上に表示されます。 たとえば、製品が、 **TypedXmlDocument** 、orderline オブジェクト以下ためになります、注文に関連付けられた**TypedXmlDocument**、orderline ではなく**TypedXmlDocument**です。 ほとんどのインスタンスで、この区別は重要ではありません。 ただし、注文オブジェクトを取り消すと、Orderline オブジェクトと Product オブジェクトも取り消されます。 Orderline オブジェクトを取り消すと、そのオブジェクトだけが取り消されます。Product オブジェクトは取り消されません。  
  
 エンジンだけを処理してオブジェクト インスタンスの追跡 (**TypedXmlDocument**s) ときに作成された、 **TypedXmlDocument**が最初にアサートされました。 他のノードを作成する場合: セレクター ポリシーで選択されたノードを兄弟ノードなど、— しない限り、これらのノードがルールで評価されません**TypedXmlDocument**s が作成され、それらのアサートします。 これらの新しい、下位のアサート**TypedXmlDocuments** 、規則が、最上位レベルで評価する**TypedXmlDocument**それらの情報を持っていません。 ときに、最上位**TypedXmlDocument**が取り消される場合、新しい、個別にアサートされた**TypedXmlDocument**自動的に取り消される場合。 その結果、新しいノードが作成される場合を取り消し、完全に再アサートする最も簡単な通常**XmlDocument**です。  
  
 **TypedXmlDocument**クラスはさまざまな操作の一部としてカスタム .NET メンバー内で呼び出すことが便利なメソッドをサポートします。 取得する機能が含まれます、 **XmlNode**に関連付けられている、 **TypedXmlDocument**または親**TypedXmlDocument**です。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 個別を撤回する**TypedDataRow**s または全体**TypedDataTable**です。 テーブルを取り消す場合、含まれるすべての行が作業メモリから取り消されます。  
  
 全体を取り消す**TypedDataTable**ヘルパー関数を使用してアクセスする必要があります、**親**プロパティ**TypedDataRow**、たとえば。  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 前のアクションでは、テーブルをドラッグして**TypedDataRow**です。 **GetTypedDataTable**の値を返すよう**TypedDataRow.Parent**です。  
  
 同様に**TypedXmlDocument**新規で追加、アサートする場合は、s、 **TypedDataRow**秒であり、同じ**DataTable**アサートの後に、 **TypedDataTable**、個々 のエンティティと取り消しとして扱われます、 **TypedDataTable**発生するわけでこれらの取り消し余分な**TypedDataRow**s。 のみ、 **TypedDataRow**に格納されている、 **TypedDataTable**がアサートされたときに取り消されます。  
  
## <a name="dataconnection"></a>DataConnection  
 ときに、 **DataConnection**が取り消される場合、すべて**TypedDataRow**によって構築されたクエリを使用して、データベースから取得される、 **DataConnection**から取り消されます作業メモリです。 **DataConnection**自体も取り消されます、つまり、これ以上ありません**TypedDataRow**s はから取得する、 **DataConnection** (つまりの使用、 **DataConnection**他の述語またはアクションで)。  
  
 使用する場合、 **DataConnection**、個別の操作を取り消し、 **TypedDataRow**が不整合な状態に、エンジンを設定します。 そのため、操作が個別の許可されていません**TypedDataRow**に関連付けられている、 **DataConnection**です。 テーブルをドラッグする場合 (を使用して、 **DataConnection**パラメーター) に、 **Retract**関数、したが取り消されます、 **DataConnection**です。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)