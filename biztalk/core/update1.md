---
title: 更新プログラム 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Update function [Business Rules Engine]
- Update function [Business Rules Engine], TypedXMLDocument
- Update function [Business Rules Engine], TypedData table
- Update function [Business Rules Engine], .NET objects
- .NET objects
- Update function [Business Rules Engine], DataConnection
ms.assetid: 939e45dc-6433-42f3-a336-8f3c247417ac
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fcb8b79b93dc2f7eeb742579afd7852dc7467a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398620"
---
# <a name="update"></a>更新
ときに**Update**関数が呼び出されたオブジェクト、オブジェクトに再アサートされて再評価されることをエンジンに基づいて、新しいデータと状態。 型のオブジェクトを指定できます**TypedXmlDocument**または .NET クラスまたは**DataConnection**または**TypedDataTable**します。  
  
 使用することも**Update**エンジンのパフォーマンスが向上し、このトピックの説明に従って、無限ループ シナリオを防止する関数。  
  
 通常、使用して**Assert** 、ルール エンジンの作業メモリに新しいオブジェクトを配置し、使用する**更新**作業メモリ内の既存のオブジェクトを更新します。 新しいオブジェクトをアサートすると、すべてのルールの条件が評価されます。 既存のオブジェクトを更新すると、更新されたファクトを使用する条件のみが再評価されます、これらの条件が評価された場合、アクションが議題に追加されますを true にします。  
  
## <a name="using-update-function-on-net-facts"></a>.NET ファクトに対する Update 関数の使用  
 例として次の 2 つのルールを実行します。 オブジェクトと**ItemA**と**ItemB**作業メモリ内に存在します。 ルール 1 の評価、 **Id**プロパティ**ItemA**、設定、 **Id**プロパティ**ItemB**、によって、および**ItemB**変更後にします。 ときに**ItemB**が再アサートされた場合は、新しいオブジェクトとして扱われ、エンジンはオブジェクトを使用するすべてのルールを再評価**ItemB**述語またはアクションにします。 これによりルール 2 の新しい値に対して再評価が**ItemB.Id**ルール 1 で設定します。 Rule 2 は、最初にそれは評価されましたに評価できなかった可能性があります**true** 2 回目に評価されます。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Assert(ItemB)  
```  
  
### <a name="rule-2"></a>Rule 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 作業メモリにオブジェクトを再度アサートするには、この機能は、順行連鎖シナリオで、動作をユーザーの明示的な制御をできます。 アサーションの副作用により、この例では副作用が Rule 1 が再評価されてもします。 **ItemA.Id**は変更されませんでした、ルール 1 にもう一度評価**true**と**assert (itemb)** 操作をもう一度起動します。 その結果、ルールは、無限ループが発生を作成します。  
  
> [!NOTE]
>  ルールの再評価の既定の最大ループ カウントが 2 ^32 です。 ルールによって、ポリシーの実行でした時間の最後の。 調整することによって、数を減らせる、**実行ループの最大の深さ**ポリシーのバージョンのプロパティ。  
  
 無限ループを作成せずにオブジェクトを再アサートできる必要があります、 **Update**関数は、この機能を提供します。 を再アサートと同様、 **Update**関数を実行します**Retract**と**Assert** 、関連付けられているオブジェクトのインスタンスのこれから変更されているルールのアクションが、2 つを使用する必要があります。主な違い:  
  
- インスタンスの型はアクション (述語ではなく) でのみ使用されているルールの議題に関するアクションが議題に維持されます。  
  
- アクションでのみインスタンスの型を使用するルールは再評価されません。  
  
  そのため、述語のみでインスタンスの種類または述語とアクションを使用するルールが再評価され、そのアクションが議題に適切に追加します。  
  
  使用する前の例を変更する、 **Update**関数によりため、ルール 2 のみが再評価される**ItemB**ルール 2 の条件に使用されます。 ルール 1 は再評価されません**ItemB**は、ループ シナリオ、ルール 1 のアクションでのみ使用します。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1  
THEN ItemB.Id = 2  
Update(ItemB)  
```  
  
### <a name="rule-2"></a>Rule 2  
  
```  
IF ItemB.Id == 2  
THEN ItemB.Value = 100  
```  
  
 ただし、ループ シナリオを作成することも可能です。 たとえば、次のルールを検討してください。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 **ItemA**される述語では、そのときに再評価されます**更新**で呼び出される**ItemA**します。 場合の値**ItemA.Id**その他の場所は変更されませんに評価されるルール 1 は**true**原因となる、 **Update** A. でもう一度呼び出されますルール デザイナーは、このようなループ シナリオは作成されないことを確認する必要があります。  
  
 これは適切なアプローチは、ルールの特性によって異なります。 上記の例では問題を解決する単純なメカニズムを次に示します。  
  
 **Update**関数は、クラスへの参照でビジネス ルール作成ツールで使用できますのと同様、 **Assert**、 **Retract**、または**RetractByType**関数。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 チェックを追加する**ItemA.Value**ルール 1 に評価されることを防ぎます**true**もう一度ルール 1 のアクションには、最初の時間が実行された後です。  
  
## <a name="using-update-function-on-xml-facts"></a>XML ファクトに対する Update 関数の使用  
 例として次の 2 つのルールを実行します。 次のものとします。 ルール 1 は、注文書メッセージ内の項目の合計数を評価し、合計数が 10 以上の場合、rule2 は"Needs approval"に状態を設定します。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count)  
```  
  
### <a name="rule-2"></a>Rule 2  
  
```  
IF ProcessPO.Order:/Order/Items/TotalCount >= 10  
THEN ProcessPO.Order:/Order/Status = "Needs approval"  
```  
  
 このポリシーへの入力として、次の発注書 (PO) メッセージを渡すと、合計項目数は 14 場合でも、状態は"Needs approval"に設定しないことがわかります。 あるため、rule2 が先頭にのみ評価されるときの値、 **TotalCount**フィールドは 0、およびルールは、合計使用可能なカウントが更新されるたびに評価されません。 条件があるたびに再評価されます、 **TotalCount**を呼び出す必要があります、更新、**更新**親ノードでの関数 (**項目**) 変更されたノード (**TotalCount**)。 次に示す Rule1 を変更して、もう一度テストして、"Needs Approval"に設定する状態フィールドの値が表示されます。  
  
```  
<ns0:Order xmlns:ns0="http://ProcessPO.Order">  
    <Items>  
        <Item>  
            <Id>ITM1</Id>  
            <Count>2</Count>  
        </Item>  
        <Item>  
            <Id>ITM2</Id>  
            <Count>5</Count>  
        </Item>  
        <Item>  
            <Id>ITM3</Id>  
            <Count>7</Count>  
        </Item>  
        <TotalCount>0</TotalCount>  
    </Items>  
    <Status>No approval needed</Status>  
</ns0:Order>  
```  
  
 変更された**ルール 1**のとおりです。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF 1 == 1  
THEN ProcessPO.Order:/Order/Items/TotalCount = (ProcessPO.Order:/Order/Items/TotalCount + ProcessPO:/Order/Items/Item/Count) AND  
Update(ProcessPO.Order:/Order/Items)  
```  
  
## <a name="using-update-function-on-database-facts"></a>データベース ファクトに対する Update 関数の使用  
  
### <a name="typeddatatable"></a>TypedDataTable  
 場合**Update**で呼び出される、 **TypedDataTable**、 **Update**は関連付けられているすべてのエンジンによって呼び出されます**TypedDataRows**します。 **Update**個人で呼び出すことができますも**TypedDataRows**します。  
  
### <a name="dataconnection"></a>DataConnection  
 更新を**DataConnection**はサポートされていません。 使用**Assert**代わりにします。  
  
## <a name="see-also"></a>参照  
 [エンジン制御関数](../core/engine-control-functions.md)