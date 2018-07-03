---
title: '手順 5: ソリューションのテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5ca5301-2ee4-4024-a90a-396ed681d12a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33a51cda93a1c2cdd6f5a70ebd62bf1d9ce05a7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020853"
---
# <a name="step-5-test-the-solution"></a>手順 5: ソリューションをテストします。
このソリューションに通知を送信するプロセスを自動化する目的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]たびに、営業案件のステージを設定して Salesforce で新しい営業案件を閉じた、 **Closed Won**します。 通知を受け取った後[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]に関連する営業案件、製品の詳細を取得する Salesforce にクエリを送信して、Salesforce からの応答をという名前の SQL Server データベース テーブルに挿入**OrderDetails**. そのため、このソリューションをテストするには更新する営業案件のステージ**Closed Won**結果として、関連するレコードを Orders データベースの [OrderDetails] テーブルで挿入取得する必要があります。  
  
### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1. Salesforce デベロッパーのログイン資格情報を使用して `https://login.salesforce.com/?lt=de` にログインします。  
  
2. ナビゲーション バーで、クリックして**機会**、順にクリックします**顧客 1 と営業案件**します。 この営業案件を作成した[手順 2: Salesforce システムを設定する](../core/step-2-set-up-the-salesforce-system.md)します。  
  
3. **営業案件の詳細**セクションで、ある関連商品をメモに取ります、**製品 (Standard)** セクション。 このセクションにある値が最終的に SQL Server データベースに挿入されます。 で、**営業案件の詳細** をクリック、**編集**ボタンをクリックしの値を変更**ステージ**フィールドを**Closed Won**します。 **[保存]** をクリックします。  
  
    ![既存の営業案件の編集](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")  
  
4. SQL Server Management studio でクエリを実行、 **OrderDetails**テーブルのすべての行を選択します。  
  
    ![SQL クエリの出力](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")  
  
    ステージを変更した営業案件に表示されていた製品の一覧が表示されることを確認してください。  
  
    ![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
   レコードの入力を参照してください、 **OrderDetails**テーブルは、製品の指定されたセットの Salesforce で作成された営業案件に対応します。 新しい営業案件を作成して、新しい製品を営業案件に関連付けることで、これらの手順を繰り返すことができます。