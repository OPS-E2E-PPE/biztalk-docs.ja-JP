---
title: '手順 2: Price and Availability プロジェクト、BizTalk エディターを使用して Contoso LOB アプリケーション スキーマの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB schemas
ms.assetid: 70e26dc9-4299-4d30-8f8b-5cc3469a2025
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f899a6614ea5d5d28c555be1b39e72b5880fe3ae
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999331"
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a>手順 2: Price and Availability プロジェクトを BizTalk エディターを使用して用の Contoso LOB アプリケーション スキーマの作成
ここでは、特定の製品の価格やその製品が入手可能かどうかを Contoso ERP システムに照会する際に使用するスキーマを生成します。 このスキーマを生成するには、BizTalk Server 用 Microsoft® SQL アダプタを使用します。  

### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a>スキーマを生成するために SQL ストアド プロシージャを更新するには  

1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリックします**SQL Server Management Studio**します。  

2.  Microsoft SQL Server Management Studio で展開**データベース**、展開**Contoso**、展開**プログラミング**、順に展開**ストアド プロシージャ**.  

3.  右クリックして**dbo します。SP_GetInventoryForProductID**、 をクリックし、**変更**します。  

4.  クエリ ウィンドウで、"for xml auto" の直後にコンマとスペースを挿入し、その後に「xmldata」と入力します。 次のコード行があります。  

    ```  
    for xml auto, xmldata  
    ```  

5.  クリックして**Execute**ストアド プロシージャに変更を保存します。  

    > [!NOTE]
    >  次の手順で使用するため、Microsoft SQL Server Management Studio は開いたままにしておきます。  

### <a name="to-create-the-contoso-price-and-availability-schema"></a>ContosoPriceAndAvailability スキーマを作成するには  

1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で Contoso ソリューションを開きます。  

2. ソリューション エクスプ ローラーで右クリックし、 **contosopriceandavailability**プロジェクトをポイントして、**追加**、 をクリックし、**生成した項目の追加**します。  

3. 生成しておきの追加 ダイアログ ボックスで**アダプター メタデータの追加**左側のウィンドウで選択されていること、**アダプター メタデータの追加**で右側のウィンドウをクリック**追加**します。  

4. **アダプターの追加ウィザード**] ページで、[ **SQL**クリックして、登録済みアダプターの一覧から**次**します。  

5. **データベース情報**] ページで [**設定**します。  

6. データ リンク プロパティ ダイアログ ボックスでの**を選択するか、サーバー名を入力**ボックスに「 **localhost**します。 選択**使用して Windows NT 統合セキュリティ**します。 **サーバー上のデータベースを選択します。** を選択、 **Contoso**データベースの一覧からデータベース。 **[OK]** をクリックします。  

7. **データベース情報**] ページで [**次**します。  

8. **スキーマ情報**ページで、次の操作を行います。  


   |                プロパティ                 |              目的              |
   |-----------------------------------------|--------------------------------------|
   |          **ターゲットの名前空間**           | 型 **<http://Contoso.com/Price>** します。 |
   |        **ポートの種類を選択します。**         |        選択**送信ポート**します。         |
   | **要求ドキュメントのルート要素名**  |      型 **[rootpricerequest]** します。      |
   | **応答ドキュメントのルート要素名** |     型**rootPriceResponse**します。      |


9. **[次へ]** をクリックします。  

10. **ステートメントの種類の情報**] ページで、[**ストアド プロシージャの**、順にクリックします**次**します。  

11. **ステートメント情報** ページの**\<ストアド プロシージャを選択\>** を選択します**SP_GetInventoryForProductID**から、ドロップダウン リスト。 クリックして**生成**、順にクリックします**次**します。  

12. **SQL トランスポート スキーマ生成ウィザードの完了**] ページで [**完了**ContosoPriceAndAvailability BizTalk プロジェクトにスキーマをインポートします。  

13. ソリューション エクスプ ローラーで、生成されたスキーマ (SQLService_Price.xsd) を右クリックして**の名前を変更**、および種類**ContosoPriceAndAvailability.xsd**スキーマの新しい名前として。 **Enter**をクリックします。  

14. ContosoPriceAndAvailability スキーマの [プロパティ] ウィンドウで、**型名**プロパティを**ContosoPriceSchema**します。  

15. 既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]という名前の BizTalk オーケストレーションを作成します。 **BizTalk Orchestration.odx**します。 このオーケストレーションを右クリックし、**削除**このオーケストレーションを必要としないためです。 オーケストレーションが完全に削除されることを示すポップアップで、次のようにクリックします。 **OK**します。  

16. Microsoft SQL Server Management Studio では、削除、`xmldata`述語とコンマから、`SP_GetInventoryForProductID`クリックして、ストアド プロシージャを前の手順で追加した**Execute**。  

## <a name="see-also"></a>参照  
 [手順 3: BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)