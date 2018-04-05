---
title: '手順 2: Price and Availability プロジェクトの BizTalk エディターを使用しての Contoso LOB アプリケーション スキーマの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 441bb90c8fa0f2edb271af384e2540a741150137
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-creating-the-contoso-lob-application-schemas-for-the-price-and-availability-project-using-biztalk-editor"></a>手順 2: Price and Availability プロジェクトの BizTalk エディターを使用して用の Contoso LOB アプリケーション スキーマの作成
ここでは、特定の製品の価格やその製品が入手可能かどうかを Contoso ERP システムに照会する際に使用するスキーマを生成します。 使用してこのスキーマを生成する、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server の SQL アダプターです。  
  
### <a name="to-update-the-sql-stored-procedure-for-schema-generation"></a>スキーマを生成するために SQL ストアド プロシージャを更新するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft SQL Server 2008 R2**、順にクリック**SQL Server Management Studio**です。  
  
2.  Microsoft SQL Server Management Studio で展開**データベース**、展開**Contoso**、展開**プログラミング**、順に展開**ストアド プロシージャ**.  
  
3.  右クリック**dbo します。SP_GetInventoryForProductID**、クリックして**変更**です。  
  
4.  クエリ ウィンドウで、"for xml auto" の直後にコンマとスペースを挿入し、その後に「xmldata」と入力します。 コードの行を以下にする必要があります。  
  
    ```  
    for xml auto, xmldata  
    ```  
  
5.  をクリックして**Execute**ストアド プロシージャに変更を保存します。  
  
    > [!NOTE]
    >  次の手順で使用するため、Microsoft SQL Server Management Studio は開いたままにしておきます。  
  
### <a name="to-create-the-contoso-price-and-availability-schema"></a>ContosoPriceAndAvailability スキーマを作成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] で Contoso ソリューションを開きます。  
  
2.  ソリューション エクスプ ローラーで右クリックし、 **ContosoPriceAndAvailability**プロジェクトをポイントし、**追加**、順にクリック**生成した項目の追加**です。  
  
3.  生成おきの追加 ダイアログ ボックスで**アダプター メタデータの追加**をクリックして選択すると、左側のウィンドウで、**アダプター メタデータの追加**をクリックして右側のウィンドウ**追加**です。  
  
4.  **アダプターの追加ウィザード**] ページで、[ **SQL**クリックして、登録されているアダプターの一覧から**次**です。  
  
5.  **データベース情報**] ページで [**設定**です。  
  
6.  [データ リンク プロパティ] ダイアログ ボックスで、**を選択するか、サーバー名を入力**ボックスに、入力**localhost**です。 選択**Windows NT 統合セキュリティ**です。 **サーバー上のデータベースを選択して**を選択、 **Contoso**データベースの一覧からデータベース。 **[OK]**をクリックします。  
  
7.  **データベース情報** ページで、をクリックして**次**です。  
  
8.  **スキーマ情報** ページで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ターゲットの名前空間**|型**http://Contoso.com/Price**です。|  
    |**ポートの種類を選択します。**|選択**送信ポート**です。|  
    |**要求ドキュメントのルート要素名**|型**rootPriceRequest**です。|  
    |**応答ドキュメントのルート要素名**|型**rootPriceResponse**です。|  
  
9. **[次へ]**をクリックします。  
  
10. **ステートメントの種類の情報**] ページで、[**ストアド プロシージャの**、順にクリック**次**です。  
  
11. **ステートメント情報**] ページの**\<ストアド プロシージャを選択\>**[ **SP_GetInventoryForProductID**から、ドロップダウン リスト。 をクリックして**生成**、クリックして**[次へ]**です。  
  
12. **SQL トランスポート スキーマ生成ウィザードを完了する** ページで、をクリックして**完了**ContosoPriceAndAvailability BizTalk プロジェクトにスキーマをインポートします。  
  
13. ソリューション エクスプ ローラーで、生成されたスキーマ (SQLService_Price.xsd) を右クリックし、をクリックして**の名前を変更**、および種類**ContosoPriceAndAvailability.xsd**スキーマの新しい名前として。 **Enter**をクリックします。  
  
14. ContosoPriceAndAvailability スキーマの [プロパティ] ウィンドウで、設定、**型名**プロパティを**ContosoPriceSchema**です。  
  
15. 既定では、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]という名前の BizTalk オーケストレーションを作成**BizTalk Orchestration.odx**です。 このオーケストレーションを右クリックし、をクリックして**削除**このオーケストレーションを必要としないためです。 オーケストレーションが完全に削除されることを示すポップアップで、をクリックして**OK**です。  
  
16. Microsoft SQL Server Management Studio では、削除、`xmldata`述語とコンマを`SP_GetInventoryForProductID`ストアド プロシージャ、前の手順で追加して、をクリックして**Execute**です。  
  
## <a name="see-also"></a>参照  
 [手順 3: BizTalk マッパーを使用した Price and Availability プロジェクト用の Contoso LOB アプリケーション マップの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)