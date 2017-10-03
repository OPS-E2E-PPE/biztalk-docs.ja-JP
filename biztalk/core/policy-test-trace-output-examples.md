---
title: "ポリシー テストのトレース出力例 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3678769dffa03bb77c3e86fef02998a354b1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="policy-test-trace-output-examples"></a>ポリシー テストのトレース出力例
このセクションでは、さまざまな種類のファクトに関するポリシー テストの出力例について説明します。  
  
## <a name="net-class"></a>.Net クラス  
 "LoanProcessing" ポリシーの "TestRule1" ルールの例:  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 ルール セットのルール エンジン トレース: LoanProcessing 2004/3/16 9時 50分: 28 AM  
  
 ファクト アクティビティ 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: MyTest.test  
  
 オブジェクト インスタンス識別子: 872  
  
 条件の評価テスト (一致) 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名: LoanProcessing  
  
 テスト式: MyTest.test.get_ID > 0  
  
 左のオペランド値: 100  
  
 右のオペランド値: 0  
  
 テスト結果: True  
  
 議題の更新 2004/3/16 9:50:28 AM  
  
 ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 実行されたルール 2004/3/16 9:50:28 AM  
  
 ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/16 9時 50分: 28 AM  
  
 ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: MyTest.test  
  
 オブジェクト インスタンス識別子: 872  
  
## <a name="dataconnectiontypeddatarow"></a>DataConnection/TypedDataRow  
 "LoanProcessing" ポリシーの "TestRule1" ルールの例:  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 ルール セットのルール エンジン トレース: LoanProcessing 2004/3/16 8時 30分: 16 AM  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: DataConnection:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 874  
  
 条件の評価テスト (一致) 2004/3/16 8:30:16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 テスト式: 選択 * [CustInfo] から、[CreditCardBalance] > 0  
  
 左側のオペランド値:   
  
 右側のオペランド値:   
  
 テスト結果: True  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177556  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177559  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177558  
  
 議題の更新 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/16 が実行されたルール 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: DataConnection:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 874  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177559  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177558  
  
 ファクト アクティビティ 2004/3/16 8時 30分: 16 AM  
  
 ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 177556  
  
 上記の例は、CustInfo テーブルの 3 つの行がルールの条件を満たしていることを示しています。  この結果、エンジンに 3 つの一意の TypedDataRows がアサートされ、議題の更新およびルール実行が各インスタンスで発生します。  
  
## <a name="typedatatabletypeddatarow"></a>TypeDataTable/TypedDataRow  
 "LoanProcessing" ポリシーの "TestRule1" ルールの例:  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **出力:**  
  
 ルール セットのルール エンジン トレース: LoanProcessing 2004/3/17 午前 11時 27分: 35  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataTable:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 377  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 376  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左のオペランド値: 500  
  
 右のオペランド値: 0  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 375  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左のオペランド値: 1000  
  
 右のオペランド値: 0  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 374  
  
 条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 左のオペランド値: 35000  
  
 右のオペランド値: 0  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataTable:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 377  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 375  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 374  
  
 ファクト アクティビティ 2004/3/17 午前 11時 27分: 35  
  
 ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedDataRow:Northwind:CustInfo  
  
 オブジェクト インスタンス識別子: 376  
  
> [!NOTE]
>  上記の例は、TypedDataTable に 3 つの行が含まれていることを示しています。各行は、TypedDataRow としてアサートされています。  各行は、条件で True として評価され、ルールが議題に追加されて実行されます。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 "LoanProcessing" ポリシーの "TestRule1" ルールの例:  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 **出力:**  
  
 ルール セットのルール エンジン トレース: LoanProcessing 2004/3/17 9時 23分: 05 AM  
  
 ファクト アクティビティ 2004/3/17 9:23:05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 オブジェクト インスタンス識別子: 858  
  
 ファクト アクティビティ 2004/3/17 9:23:05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 操作: アサート  
  
 オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 オブジェクト インスタンス識別子: 853  
  
 条件の評価テスト (一致) 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 テスト式: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths > 4 を =  
  
 左のオペランド値: 6  
  
 右のオペランド値: 4  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 操作: 追加  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール 9時 23分: 05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 ルール名: TestRule1  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 9:23:05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 オブジェクト インスタンス識別子: 858  
  
 ファクト アクティビティ 2004/3/17 9:23:05 AM  
  
 ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 ルール セット名: LoanProcessing  
  
 操作: 取り消し  
  
 オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 オブジェクト インスタンス識別子: 853  
  
 次の例、 **TypedXmlDocument** "microsoft.samples.biztalk.loansprocessor.case"というのドキュメントの種類を使用してエンジンにアサートされました。  次に、ルールで定義された XPath セレクターに応じて、エンジンは、ドキュメントの種類とセレクターの文字列に基づいた "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" の子 TypedXmlDocument を作成してアサートします。  
  
 この子 TypedXmlDocument は、条件で True に評価されたため、議題の更新やルールの実行が行われます。  親と子**TypedXmlDocument**が取り消されます。  
  
## <a name="update-function"></a>Update 関数  
 "Order" ポリシーの例  
  
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
  
 ルール セットのルール エンジン トレース: Order 2004/3/17 10時 31分: 17 AM  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: アサート  
  
 オブジェクトの種類: TestClasses.Order  
  
 オブジェクト インスタンス識別子: 448  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 テスト式: TestClasses.Order.inventoryAvailable = = True  
  
 左のオペランド値: null  
  
 右のオペランド値: True  
  
 テスト結果: False  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: アサート  
  
 オブジェクトの種類: TestClasses.Shipment  
  
 オブジェクト インスタンス識別子: 447  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: アサート  
  
 オブジェクトの種類: TestClasses.Inventory  
  
 オブジェクト インスタンス識別子: 446  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 テスト式: TestClasses.Inventory.AllocateInventory = = True  
  
 左のオペランド値: True  
  
 右のオペランド値: True  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 追加  
  
 ルール名: InventoryCheck  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 ルール名: InventoryCheck  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 更新プログラム  
  
 オブジェクトの種類: TestClasses.Order  
  
 オブジェクト インスタンス識別子: 448  
  
 条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 テスト式: TestClasses.Order.inventoryAvailable = = True  
  
 左のオペランド値: True  
  
 右のオペランド値: True  
  
 テスト結果: True  
  
 議題の更新 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 追加  
  
 ルール名: 出荷  
  
 競合解決条件: 0  
  
 2004/3/17 が実行されたルール 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 ルール名: 出荷  
  
 競合解決条件: 0  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 取り消し  
  
 オブジェクトの種類: TestClasses.Order  
  
 オブジェクト インスタンス識別子: 448  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 取り消し  
  
 オブジェクトの種類: TestClasses.Shipment  
  
 オブジェクト インスタンス識別子: 447  
  
 ファクト アクティビティ 2004/3/17 10時 31分: 17 AM  
  
 ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 ルール セット名: 順序  
  
 操作: 取り消し  
  
 オブジェクトの種類: TestClasses.Inventory  
  
 オブジェクト インスタンス識別子: 446  
  
 この例では、Ship ルールに関連付けられている条件が最初に確認されるときに False と評価されます。  ただし、InventoryCheck ルールが実行されると、Order オブジェクトの inventoryAvailable フィールドが変更され、Update コマンドが Order オブジェクトのエンジンで発行されます。  このため、Ship ルールが再評価されます。  今回の条件は True に評価され、Ship ルールが実行されます。  
  
> [!NOTE]
>  ルールが不正確に書き込まれると、Update 関数の前向き連鎖で、無限ループに陥る可能性があります。  無限ループが発生すると、ビジネス ルール作成ツールのポリシーをテストするときに、"ルール エンジンが実行ループを検出しました。" というエラー メッセージが表示されます。