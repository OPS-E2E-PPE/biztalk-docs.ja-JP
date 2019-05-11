---
title: ポリシー テストのトレース出力の例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 365d962c7a21721e75eb3c0c5abd6e2d93bfd5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394948"
---
# <a name="policy-test-trace-output-examples"></a>ポリシー テストのトレース出力例
このセクションでは、さまざまな種類のファクトをポリシーのテストの出力の例を示します。  
  
## <a name="net-class"></a>.Net クラス  
 "LoanProcessing"ポリシーの例のルール"TestRule1":  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 セットのルール エンジン トレース:LoanProcessing 2004/3/16 9時 50分: 28 AM  
  
 ファクト アクティビティ 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:MyTest.test  
  
 オブジェクト インスタンス識別子:872  
  
 条件の評価テスト (一致) 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名:LoanProcessing  
  
 テスト式。MyTest.test.get_ID > 0  
  
 左側のオペランド値:100  
  
 右側のオペランド値:0  
  
 テスト結果。True  
  
 議題の更新 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/16 が実行されたルール 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:MyTest.test  
  
 オブジェクト インスタンス識別子:872  
  
## <a name="dataconnectiontypeddatarow"></a>DataConnection/TypedDataRow  
 "LoanProcessing"ポリシーの例のルール"TestRule1":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 セットのルール エンジン トレース:LoanProcessing 2004/3/16 8時 30分: 16 AM  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:DataConnection:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:874  
  
 条件の評価テスト (一致) 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 Test Expression: select * from [CustInfo] where [CreditCardBalance] > 0  
  
 左側のオペランド値:  
  
 右側のオペランド値:  
  
 テスト結果。True  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177556  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177559  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177558  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:DataConnection:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:874  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177559  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177558  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:177556  
  
 上記の例では、CustInfo テーブルの 3 つの行に、ルールの条件が満たされていることを示します。  これにより、エンジンと、議題の更新と各インスタンスに対して発生するルールの実行がアサートする 3 つの一意な TypedDataRows が発生します。  
  
## <a name="typedatatabletypeddatarow"></a>TypeDataTable/TypedDataRow  
 "LoanProcessing"ポリシーの例のルール"TestRule1":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 セットのルール エンジン トレース:LoanProcessing 2004/3/17 午前 11時 27分: 35  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataTable:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:377  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:376  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左側のオペランド値:500  
  
 右側のオペランド値:0  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:375  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左側のオペランド値:1000  
  
 右側のオペランド値:0  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:374  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左側のオペランド値:35000  
  
 右側のオペランド値:0  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataTable:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:377  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:375  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:374  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子:376  
  
> [!NOTE]
>  上記の例は、TypedDataTable に 3 つの行が含まれているし、それぞれが、TypedDataRow としてアサートされたことを示します。  ルールが議題に追加して、発生した各条件で True に評価します。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 "LoanProcessing"ポリシーの例のルール"TestRule1":  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 **出力:**  
  
 セットのルール エンジン トレース:LoanProcessing 2004/3/17 9時 23分: 05 AM  
  
 ファクト アクティビティ 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 オブジェクト インスタンス識別子:858  
  
 ファクト アクティビティ 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 操作:Filter  
  
 オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 オブジェクト インスタンス識別子:853  
  
 条件の評価テスト (一致) 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 テスト式。TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
  
 左側のオペランド値:6  
  
 右側のオペランド値:4  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 操作:[追加]  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 ルール名:TestRule1  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 オブジェクト インスタンス識別子:858  
  
 ファクト アクティビティ 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名:LoanProcessing  
  
 操作:取り消し  
  
 オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 オブジェクト インスタンス識別子:853  
  
 この例では、 **TypedXmlDocument** "microsoft.samples.biztalk.loansprocessor.case"というのドキュメントの種類を使用してエンジンにアサートされました。  ルールで定義された XPath セレクターに基づいて、エンジンを作成し、ドキュメントの種類とセレクターの文字列に基づいて"Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType"の種類と子 TypedXmlDocument をアサートします。  
  
 この子 TypedXmlDocument 条件で True に評価された、議題の更新とルールの実行が原因です。  親と子**TypedXmlDocument**の取り消されたします。  
  
## <a name="update-function"></a>Update 関数  
 "Order"のポリシーの例  
  
 **"InventoryCheck"ルール**  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 **"Ship"ルール**  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 **出力:**  
  
 セットのルール エンジン トレース:2004/3/17 の注文 10時 31分: 17 AM  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:Filter  
  
 オブジェクトの種類:TestClasses.Order  
  
 オブジェクト インスタンス識別子:448  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 テスト式。TestClasses.Order.inventoryAvailable == True  
  
 左のオペランド値: null  
  
 右側のオペランド値:True  
  
 テスト結果。False  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:Filter  
  
 オブジェクトの種類:TestClasses.Shipment  
  
 オブジェクト インスタンス識別子:447  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:Filter  
  
 オブジェクトの種類:TestClasses.Inventory  
  
 オブジェクト インスタンス識別子:446  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 テスト式。TestClasses.Inventory.AllocateInventory == True  
  
 左側のオペランド値:True  
  
 右側のオペランド値:True  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:[追加]  
  
 ルール名:InventoryCheck  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 ルール名:InventoryCheck  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:更新  
  
 オブジェクトの種類:TestClasses.Order  
  
 オブジェクト インスタンス識別子:448  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 テスト式。TestClasses.Order.inventoryAvailable == True  
  
 左側のオペランド値:True  
  
 右側のオペランド値:True  
  
 テスト結果。True  
  
 議題の更新 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:[追加]  
  
 ルール名:出荷  
  
 競合解決条件:0  
  
 2004/3/17 が実行されたルール 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 ルール名:出荷  
  
 競合解決条件:0  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:取り消し  
  
 オブジェクトの種類:TestClasses.Order  
  
 オブジェクト インスタンス識別子:448  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:取り消し  
  
 オブジェクトの種類:TestClasses.Shipment  
  
 オブジェクト インスタンス識別子:447  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名:[オーダー]  
  
 操作:取り消し  
  
 オブジェクトの種類:TestClasses.Inventory  
  
 オブジェクト インスタンス識別子:446  
  
 この例では、Ship ルールに関連付けられている条件は、最初に確認されるときを False に評価されます。  ただし、InventoryCheck ルールが発生したときは、順序の inventoryAvailable フィールドが変更され、Order オブジェクトのエンジンに対して、Update コマンドが実行されました。  これにより、Ship ルールが再評価されます。  この時間条件を true と評価、Ship ルールが起動します。  
  
> [!NOTE]
>  ルールが正しく書き込まれた、前向き連鎖更新関数で、無限ループことがあります。  この場合、メッセージが表示されます、エラー テキストを含むビジネス ルール作成ツールでポリシーをテストするときに「ルール エンジンの検出は実行ループを」