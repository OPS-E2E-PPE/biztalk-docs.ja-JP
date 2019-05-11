---
title: 取り消し |Microsoft Docs
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
ms.openlocfilehash: 94967d573bf4293c0a2dcf6bf6c718f79d19736f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399083"
---
# <a name="retract"></a>取り消し
使用することができます、 **Retract**ビジネス ルール エンジンの作業メモリからオブジェクトを削除する関数。 次の段落では、ルール エンジンの作業メモリからさまざまな種類のエンティティを取り消す操作に関連付けられている動作を説明します。  
  
## <a name="net-objects"></a>.NET オブジェクト  
 ポリシーを使用して .NET オブジェクトが取り消され、 **Retract**関数。 この関数は、ビジネス ルール作成ツールとして、**関数**ボキャブラリ項目: (しないアセンブリまたはメソッド) のクラスをドラッグ、 **Retract**パラメーター。  
  
> [!NOTE]
>  メソッドをドラッグする場合、 **Retract**関数、エンジンは、メソッドによって返されるオブジェクトを取り消すとします。  
  
 .NET オブジェクトを取り消すと、ルール エンジンの作業メモリから削除されます、次の影響します。  
  
-   述語でオブジェクトを使用する規則があるアクションを (議題にある) 場合、議題から削除します。  
  
-   オブジェクトを使用する議題のアクションは、議題から削除されます。  
  
    > [!NOTE]
    >  前に、その他のアクションが議題の上位を既に実行されている可能性があります、 **Retract**関数が呼び出されました。  
  
-   オブジェクトは、不要になったエンジンによって評価されます。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 元を取り消すことができますか**TypedXmlDocument**をエンジンにアサートされたまたは子の 1 つを取り消す**TypedXmlDocument**の親ノードから作成された s **XmlDocument**.  
  
 例として、次の XML を使用することができます取り消すか、 **TypedXmlDocument**順序または 1 つまたは両方に関連付けられている、 **TypedXmlDocument**s orderline に関連付けられています。  
  
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
  
 注文オブジェクトを取り消すには、XML スキーマ ファクト ペインで、スキーマの最上位ノードをドラッグします。 このノードが".xsd"で終わるし、ドキュメントのルート ノード (ドキュメントの要素ノードではなく); を表します最初に参照する「/」セレクターが**TypedXmlDocument**します。 ときに、親**TypedXmlDocument**が取り消される場合、すべて**TypedXmlDocument**インスタンスに関連付けられている、 **TypedXmlDocument** (すべて**TypedXmlDocument**呼び出すことによって作成された、 **Assert**関数は、ポリシーで使用されるセレクターに基づく) が作業メモリから削除します。  
  
 取り消すには、個々 の子のみ**TypedXmlDocument** (つまり、orderline) に XML スキーマ ペインからこのノードをドラッグすることができます、 **Retract**関数。 重要な点がすべて**TypedXmlDocument**s は、最上位レベルに関連付けられた**TypedXmlDocument**を最初にアサートされたではなく、 **TypedXmlDocument**XML ツリーの階層で上位に表示されます。 たとえば、製品は、 **TypedXmlDocument** orderline オブジェクト; の下、なります、注文に関連付けられて**TypedXmlDocument**、orderline ではなく**TypedXmlDocument**します。 ほとんどの状況では、この区別は重要ではありません。 ただし、order オブジェクトを取り消す場合も、orderline オブジェクトと product オブジェクトが取り消されます。 Orderline オブジェクトを取り消す場合は、そのオブジェクトのみが取り消され、および製品オブジェクトではありません。  
  
 エンジンでのみ動作し、トラック オブジェクト インスタンス (**TypedXmlDocument**s) ときに作成する、 **TypedXmlDocument**が最初にアサートされました。 他のノードを作成する場合: セレクター、ポリシーで選択されたノードに対する兄弟ノードなど、しない限り、これらのノードがルールで評価されません**TypedXmlDocument**s が作成され、それらのアサートします。 これらの新しいより低いレベル アサート**TypedXmlDocuments**によってそれらの規則が最上位レベルで評価される**TypedXmlDocument**それらの情報を持っていません。 ときに、最上位**TypedXmlDocument**が取り消される場合、新しい、個別にアサートされた**TypedXmlDocument**自動的に取り消される場合。 その結果、新しいノードを作成すると、あるを取り消し、完全な再アサートする最も簡単な通常**XmlDocument**します。  
  
 **TypedXmlDocument**クラスは、さまざまなアクションの一部としてカスタム .NET メンバー内で呼び出すことができる便利なメソッドをサポートしています。 取得する機能が含まれます、 **XmlNode**に関連付けられている、 **TypedXmlDocument**または親**TypedXmlDocument**します。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 どちらにもを撤回する**TypedDataRow**全体または**TypedDataTable**します。 テーブルを取り消す場合、含んでいるすべての行は作業メモリから取り消されます。  
  
 全体を取り消す**TypedDataTable**ヘルパー関数を使用してアクセスする必要があります、**親**プロパティ**TypedDataRow**、たとえば。  
  
```  
Retract(MyHelper.GetTypedDataTable(TypedDataRow))  
```  
  
 前のアクションでは、テーブルをドラッグして**TypedDataRow**します。 **GetTypedDataTable**の値を返すよう**TypedDataRow.Parent**します。  
  
 同様**TypedXmlDocument**新規で追加すると、アサートする場合は、s、 **TypedDataRow**の同じ**DataTable**アサートした後、 **TypedDataTable**、個々 のエンティティと縮小として扱われます、 **TypedDataTable**は行われませんこれらの取り消しで余分な**TypedDataRow**秒。 のみ、 **TypedDataRow**に格納されている、 **TypedDataTable**がアサートされたときに取り消されます。  
  
## <a name="dataconnection"></a>DataConnection  
 ときに、 **DataConnection**が取り消される場合、すべて**TypedDataRow**によって構築されたクエリを使用して、データベースから取得される、 **DataConnection**がから取り消されます作業メモリ。 **DataConnection**も取り消されます、つまり、これ以上ありません**TypedDataRow**s を通じて取得は、 **DataConnection** (つまり、までの使用、 **DataConnection**他の述語またはアクションで)。  
  
 使用する場合、 **DataConnection**、個々 の操作を取り消し、 **TypedDataRow**エンジンは、不整合な状態にします。 そのため、操作が個別に許可されていません**TypedDataRow**に関連付けられている、 **DataConnection**します。 テーブルをドラッグする場合 (を使用して、 **DataConnection**パラメーター) に、 **Retract**関数、したが取り消されます、 **DataConnection**します。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)