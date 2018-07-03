---
title: A4SWIFT データベース内の Bicplus テーブルを管理する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a3988a7b86d3f31365019c10cdfb640313dc2d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010683"
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a>A4SWIFT データベース内の Bicplus テーブルを管理します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BIC エントリのテーブルを使用すると、BIC 検証を実行します。 このテーブルの Bicplus テーブルを指定できます、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースまたはカスタムのデータベース内のテーブル。  
  
 このテーブルを管理するには、SWIFT からの BIC 値で設定する必要があります。 SQL ビューをエクスポートする必要がありますも、カスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム データベースへのデータベース。  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a>SWIFT Bicplus データベースから BIC データのインポート  
 SWIFT から BIC 値を持つ BIC エントリ (既定またはカスタムのテーブル) のテーブルを構成する必要があります。 SWIFT BIC データが表示されます、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートまたは Oracle データベースは毎月更新されます。 SWIFT BIC データの詳細についてを参照してください[ http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)します。  
  
 カスタム データベースを使用する場合は、カスタムのデータベースに SWIFT Bicplus データベースから BIC データをエクスポートする必要があります。 しなきゃいけません  
  
 データをインポートするには、BIC から[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシート内の Bicplus テーブルに SWIFT によって提供される、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースの互換性があるので。 以外に、SWIFT スプレッドシートからデータをインポートする[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース フィールドおよび BIC 列では特に、データベース内の列と SWIFT のスプレッドシートと互換性があるかどうかを確認してください。  
  
 インポート操作では、SWIFT テーブルで公開されているコードを変換先テーブルを更新する際、発行されていない BIC コードは削除されません。  
  
 Bicplus テーブルへの変更、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース ログイン、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ファイル。  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a>SWIFT Bicplus データベースから BIC データをインポートするには  
  
1. をクリックして**開始**、] をポイント**すべてのプログラム**inistalled バージョンの SQL Server の場合をポイントし、[クリックして**SQL Server Management Studio**します。  
  
2. [サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。  
  
3. Microsoft SQL Server Management Studio ウィンドウで、サーバー ノードを展開し、**データベース**します。  
  
4. 右クリック**A4SWIFT**、 をポイント**タスク**、 をクリックし、**データのインポート**します。  
  
5. SQL Server インポートおよびエクスポート ウィザードの [ようこそ] ページで、をクリックして**次**します。  
  
6. **データ ソースの選択**SWIFT Bicplus から BIC データをインポートする場合、ページ[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートで、 **Excel**で、**データ ソース**テキスト ボックス。 スプレッドシートの場所を参照して、スプレッドシート内のファイル名を選択、 **Excel ファイル パス**テキスト ボックス。 **[次へ]** をクリックします。  
  
    Oracle データベースから BIC データをインポートする場合は、選択**Microsoft ODBC Driver for Oracle**で、**データソース**テキスト ボックス。 Oracle データベースとユーザー名と、そのサーバーに接続し、をクリックし、必要なパスワードを使用して、サーバーを入力します。**次**します。  
  
7. **変換先の選択**ことを確認します ページで、 **Microsoft OLE DB Provider for SQL Server**が入力されて、**先**テキスト ボックスで、**使用Windows 認証**が選択されています。 内の Bicplus テーブルを作成する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースであることを確認**A4SWIFT**が入力されて、**データベース**テキスト ボックス。 カスタム データベースを使用している場合は、そのデータベースの名前を入力、**データベース**テキスト ボックス。 **[次へ]** をクリックします。  
  
8. **選択テーブルのコピーまたはクエリ**ことを確認します ページで、 **1 つまたは複数のテーブルまたはビューからデータをコピー**が選択されています。 データを指定するには、選択クエリを使用する必要がある場合**を転送するデータを指定するクエリを記述**します。 **[次へ]** をクリックします。  
  
9. **選択元のテーブルおよびビュー** ] ページで [ **Bicplus**で、**ソース**列を選択**Bicplus**で、 **変換先**列、およびクリック**次**します。  
  
10. **実行パッケージの保存および** ページで、適切なスケジュール情報を入力してをクリックし、**次**。  
  
11. **ウィザードを完了** ページで概要を確認してクリックして**完了**します。  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a>カスタム データベース A4SWIFT データベースから SQL ビューにインポートします。  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムによって 2 つの SQL ビュー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。 1 つのビューは 8 文字 BICs あり、11 文字 BICs 用、もう一方は。  
  
 代わりにカスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、カスタム データベースにこれらの SQL ビューをインポートする必要があります。 クエリ アナライザーで CreateBICViews.sql スクリプトを実行してこれを行います。 このスクリプトは\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT/スクリプト。  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a>A4SWIFT データベースからカスタムのデータベースに SQL ビューをインポートするには  
  
1.  Windows エクスプ ローラーで、移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts します。 ダブルクリック**CreateBICViews.sql**します。  
  
2.  [サーバー] ダイアログ ボックスへの接続、クリックして**Connect**します。  
  
3.  Microsoft SQL Server Management Studio ウィンドウで、次のように選択します。 **A4SWIFT**データベース テキスト ボックスをオンにします。  
  
4.  BICs"Bicplus"以外の名前はテーブル内に格納する場合が検索クエリ ペインで**dbo します。Bicplus**ビューで**dbo します。Bic11**、適切なテーブル名に変更します。 ビューの同じ操作を行います**dbo します。Bic8**します。  
  
5.  BICs を"BIC"以外の名前は列に格納する場合は、検索**BIC**で、**選択**、**場所**、および**ORDER BY**句、および適切な列の名前に変更します。  
  
6.  **[実行]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [銀行識別コードの検証の有効化](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)