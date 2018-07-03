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
ms.openlocfilehash: ccb9c8e8b75bc67954c30bf2b4a6e6ff39b3ee01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008827"
---
# <a name="update"></a>更新
ときに**Update**関数が呼び出されたオブジェクト、オブジェクトに再アサートされて再評価されることをエンジンに基づいて、新しいデータと状態。 型のオブジェクトを指定できます**TypedXmlDocument**または .NET クラスまたは**DataConnection**または**TypedDataTable**します。  
  
 使用することも**Update**エンジンのパフォーマンスが向上し、このトピックの説明に従って、無限ループ シナリオを防止する関数。  
  
 通常、使用して**Assert** 、ルール エンジンの作業メモリに新しいオブジェクトを配置し、使用する**更新**作業メモリ内の既存のオブジェクトを更新します。 新しいオブジェクトをアサートすると、すべてのルールの条件が評価されます。 既存のオブジェクトを更新すると、更新されたファクトを使用する条件のみ再評価され、これらの条件が true に評価された場合にアクションが議題に追加されます。  
  
## <a name="using-update-function-on-net-facts"></a>.NET ファクトに対する Update 関数の使用  
 例として 2 つのルールを示します。 オブジェクトと**ItemA**と**ItemB**作業メモリ内に存在します。 ルール 1 の評価、 **Id**プロパティ**ItemA**、設定、 **Id**プロパティ**ItemB**、によって、および**ItemB**変更後にします。 ときに**ItemB**が再アサートされた場合は、新しいオブジェクトとして扱われ、エンジンはオブジェクトを使用するすべてのルールを再評価**ItemB**述語またはアクションにします。 これによりルール 2 の新しい値に対して再評価が**ItemB.Id**ルール 1 で設定します。 Rule 2 は、最初にそれは評価されましたに評価できなかった可能性があります**true** 2 回目に評価されます。  
  
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
  
 オブジェクトを作業メモリに再度アサートする機能により、ユーザーは、順行連鎖シナリオでの動作を明示的に制御できます。 しかし、この例では再アサーションの副作用により、ルール 1 も再評価されます。 **ItemA.Id**は変更されませんでした、ルール 1 にもう一度評価**true**と**assert (itemb)** 操作をもう一度起動します。 その結果、無限ループが発生します。  
  
> [!NOTE]
>  ルールの再評価の既定の最大ループ カウントが 2 ^32 です。 ルールによって、ポリシーの実行でした時間の最後の。 調整することによって、数を減らせる、**実行ループの最大の深さ**ポリシーのバージョンのプロパティ。  
  
 無限ループを作成せずにオブジェクトを再アサートできる必要があります、 **Update**関数は、この機能を提供します。 を再アサートと同様、 **Update**関数を実行します**Retract**と**Assert** 、関連付けられているオブジェクトのインスタンスのこれから変更されているルールのアクションが、2 つを使用する必要があります。主な違い:  
  
- そのインスタンスの種類が述語ではなくアクションのみで使用されるルールでは、議題に含まれるアクションが議題に維持されます。  
  
- そのインスタンスの種類をアクションのみで使用するルールは再評価されません。  
  
  したがって、述語のみ、または述語とアクションの両方でインスタンスの種類を使用するルールが再評価され、そのアクションが議題に適切に追加されます。  
  
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
  
 しかし、まだループ シナリオが発生する可能性があります。 たとえば、次のルールを検討してください。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 **ItemA**される述語では、そのときに再評価されます**更新**で呼び出される**ItemA**します。 場合の値**ItemA.Id**その他の場所は変更されませんに評価されるルール 1 は**true**原因となる、 **Update** A. でもう一度呼び出されますルール デザイナーは、このようなループ シナリオは作成されないことを確認する必要があります。  
  
 この場合の適切なアプローチは、ルールの特性により異なります。 前の例の問題を解決するための簡単なメカニズムを次に示します。  
  
 **Update**関数は、クラスへの参照でビジネス ルール作成ツールで使用できますのと同様、 **Assert**、 **Retract**、または**RetractByType**関数。  
  
### <a name="rule-1"></a>ルール 1  
  
```  
IF ItemA.Id == 1 and ItemA.Value != 20  
THEN ItemA.Value = 20  
Update(ItemA)  
```  
  
 チェックを追加する**ItemA.Value**ルール 1 に評価されることを防ぎます**true**もう一度ルール 1 のアクションには、最初の時間が実行された後です。  
  
## <a name="using-update-function-on-xml-facts"></a>XML ファクトに対する Update 関数の使用  
 例として 2 つのルールを示します。 次のものとします。 ルール 1 では注文書メッセージの項目の合計数を評価します。合計数が 10 以上である場合、ルール 2 により状態は "Needs approval" に設定されます。  
  
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
  
 このポリシーへの入力として、次の発注書 (PO) メッセージを渡すと、合計項目数は 14 場合でも、状態は"Needs approval"に設定しないことがわかります。 あるため、rule2 が先頭にのみ評価されるときの値、 **TotalCount**フィールドは 0、およびルールは、合計使用可能なカウントが更新されるたびに評価されません。 条件があるたびに再評価されます、 **TotalCount**を呼び出す必要があります、更新、**更新**親ノードでの関数 (**項目**) 変更されたノード (**TotalCount**)。 ルール 1 を次に示すように変更し、もう一度テストすると、Status フィールドの値は "Needs Approval" に設定されます。  
  
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