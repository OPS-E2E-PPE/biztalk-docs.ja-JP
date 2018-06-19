---
title: '手順 5: ソリューションのテスト |Microsoft ドキュメント'
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
ms.openlocfilehash: 7ce7edd1c1f1f8a063e2787cc2acecb3b57cca2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276890"
---
# <a name="step-5-test-the-solution"></a>手順 5: ソリューションをテストします。
このソリューションの目的に通知を送信するプロセスを自動化する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]たびに、営業案件のステージを設定して Salesforce で新しい営業案件が閉じられた、 **Closed Won**です。 通知の受信後に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、営業案件に関連する製品詳細を取得する Salesforce にクエリを送信し、Salesforce から応答をという名前の SQL Server データベース テーブルに挿入**OrderDetails**. そのため、このソリューションをテストするには更新に営業案件のステージ**Closed Won**結果として、関連レコードを Orders データベースの [OrderDetails] テーブルで挿入取得する必要があります。  
  
### <a name="to-test-the-solution"></a>ソリューションをテストするには、次の操作を行います。  
  
1.  Salesforce デベロッパーのログイン資格情報を使用して `https://login.salesforce.com/?lt=de` にログインします。  
  
2.  ナビゲーション バーで、クリックして**機会**、順にクリック**顧客 1 との営業案件**です。 この営業案件を作成した[手順 2: Salesforce システムのセットアップ](../core/step-2-set-up-the-salesforce-system.md)です。  
  
3.  **営業案件の詳細**セクションに関連付けられている製品のメモ、**製品 (標準)** セクションです。 このセクションにある値が最終的に SQL Server データベースに挿入されます。 下にある、**営業案件の詳細** をクリック、**編集**ボタンをクリックしの値を変更**ステージ**フィールドを**Closed Won**です。 **[保存]** をクリックします。  
  
     ![既存の営業案件の編集](../core/media/bts-sf-edit-opp.jpg "BTS_SF_Edit_Opp")  
  
4.  SQL Server Management Studio でのクエリを実行、 **OrderDetails**テーブルのすべての行を選択します。  
  
     ![SQL Query 出力](../core/media/bts-sf-sql-query.jpg "BTS_SF_SQL_Query")  
  
     ステージを変更した営業案件に表示されていた製品の一覧が表示されることを確認してください。  
  
     ![営業案件に製品を追加](../core/media/bts-sf-add-product.gif "BTS_SF_Add_Product")  
  
 レコードに入力したことを確認できます、 **OrderDetails**テーブルは、Salesforce での製品の指定されたセットの作成の営業案件に対応します。 新しい営業案件を作成して、新しい製品を営業案件に関連付けることで、これらの手順を繰り返すことができます。