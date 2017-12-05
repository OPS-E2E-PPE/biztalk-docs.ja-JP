---
title: "A4SWIFT データベース内の Bicplus テーブルを管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a58396a9dd6627f2913da8e3845a99b17cf7698
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a>A4SWIFT データベース内の Bicplus テーブルを管理します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BIC 検証を実行するのにには、BIC エントリのテーブルを使用します。 このテーブルがで Bicplus テーブルにすることができます、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースまたはカスタムのデータベース内のテーブルです。  
  
 このテーブルを管理するには、SWIFT から BIC 値を設定する必要があります。 SQL ビューをエクスポートするカスタム データベースを使用する場合もする必要があります、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]カスタム データベースにデータベース。  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a>SWIFT Bicplus データベースから BIC データのインポート  
 SWIFT から BIC 値を持つ BIC エントリ (既定またはカスタムのテーブル) のテーブルを構成する必要があります。 SWIFT BIC データが使用する[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートまたは毎月更新される Oracle データベースでします。 SWIFT BIC データに関する詳細についてを参照してください[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)です。  
  
 カスタム データベースを使用する場合は、カスタムのデータベースに SWIFT Bicplus データベースから BIC データをエクスポートする必要があります。 しなきゃいけません  
  
 BIC からデータをインポートすることができます[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートの Bicplus テーブルに SWIFT によって提供される、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースの互換性があるためです。 以外に、SWIFT、スプレッドシートからデータをインポートするかどうかは[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、フィールドおよび BIC 列では特に、データベース内の列に SWIFT のスプレッドシートと互換性があるかどうかを確認します。  
  
 インポート操作では、SWIFT テーブルでパブリッシュされたコードをコピー先のテーブルを更新するとき、パブリッシュされていない BIC コードは削除されません。  
  
 Bicplus テーブルへの変更、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース ログイン、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ログ ファイルです。  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a>SWIFT Bicplus データベースから BIC データをインポートするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**inistalled のバージョンの SQL Server をポイントし、クリックして**SQL Server Management Studio**です。  
  
2.  [サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。  
  
3.  Microsoft SQL Server Management Studio ウィンドウで、サーバー ノードを展開し、**データベース**です。  
  
4.  右クリック**A4SWIFT**、 をポイント**タスク**、クリックして**データのインポート**です。  
  
5.  SQL Server インポートおよびエクスポート ウィザードへようこそ ページで、をクリックして**次**です。  
  
6.  **データ ソースを選択**ページに SWIFT Bicplus から BIC データをインポートする場合、[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]スプレッドシートで、 **Microsoft Excel**で、**データソース**テキスト ボックス。 スプレッドシートの場所を参照して、スプレッドシート内のファイル名を選択、 **Excel ファイル パス**テキスト ボックス。 **[次へ]**をクリックします。  
  
     Oracle データベースから BIC データをインポートする場合は、選択**Microsoft ODBC Driver for Oracle**で、**データソース**テキスト ボックス。 Oracle データベースとユーザー名と、そのサーバーに接続し、をクリックし、必要なパスワードを使用してサーバーを入力**次**です。  
  
7.  **変換先を選択**ことを確認 ページで、 **Microsoft OLE DB Provider for SQL Server**で入力した、**先**テキスト ボックスで、**使用Windows 認証**が選択されています。 Bicplus のテーブルを作成する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベースであることを確認**A4SWIFT**で入力した、**データベース**テキスト ボックス。 カスタム データベースを使用している場合は、そのデータベースでの名前を入力、**データベース**テキスト ボックス。 **[次へ]**をクリックします。  
  
8.  **選択テーブルのコピーまたはクエリ**ことを確認 ページで、 **1 つまたは複数のテーブルまたはビューからデータをコピー**が選択されています。 選択をデータを指定するクエリを使用する必要がある場合**を転送するデータを指定するクエリを記述**です。 **[次へ]**をクリックします。  
  
9. **[ソース テーブルおよびビュー** ] ページで、をクリックして**Bicplus**で、**ソース**列を選択**Bicplus**で、 **移行先**列、およびクリック**次**です。  
  
10. **を保存してパッケージ実行** ページで、適切なスケジュール情報を入力してをクリックして**次**です。  
  
11. **ウィザードを完了** ページで概要を確認してをクリックして**完了**です。  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a>カスタム データベース A4SWIFT データベースからの SQL ビューにインポートします。  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ プログラムによって、2 つの SQL ビュー、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース。 1 つのビューは 8 文字 BICs と 11 文字 BICs は、他のです。  
  
 代わりにカスタム データベースを使用する場合、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]データベース、カスタムのデータベースにこれらの SQL ビューをインポートする必要があります。 クエリ アナライザーで CreateBICViews.sql スクリプトを実行するようにします。 このスクリプトが\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT/スクリプト。  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a>カスタム データベースに A4SWIFT データベースからの SQL ビューをインポートするには  
  
1.  Windows エクスプローラで、移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts です。 ダブルクリックして**CreateBICViews.sql**です。  
  
2.  [サーバー] ダイアログ ボックスへの接続でクリックして**接続**です。  
  
3.  Microsoft SQL Server Management Studio ウィンドウで選択**A4SWIFT**データベース テキスト ボックスにします。  
  
4.  クエリ ウィンドウで BICs を"Bicplus"以外のという名前のテーブルに格納する場合が見つけ**dbo します。Bicplus**ビューで**dbo します。Bic11**、適切なテーブル名に変更します。 ビューの同じ**dbo します。Bic8**です。  
  
5.  BICs を"BIC"以外の名前は、列に格納する場合は、検索**BIC**で、**選択**、**場所**、および**ORDER BY**句、および適切な列の名前に変更します。  
  
6.  **[実行]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [銀行識別コードの検証の有効化](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)