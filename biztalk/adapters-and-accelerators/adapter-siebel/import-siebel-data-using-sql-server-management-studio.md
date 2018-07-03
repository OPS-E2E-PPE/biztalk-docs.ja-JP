---
title: SQL Server Management Studio を使用して Siebel データのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdcc6140bb50ebca299cd58f78063be8f108dea4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013179"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a>SQL Server Management Studio を使用して Siebel データをインポートします。
このセクションでは、SQL Server Management Studio を使用して Siebel システムから SQL Server データベースにデータをインポートする方法について説明します。 また、作成し、このデータをインポートする SSIS パッケージを実行する方法の手順を提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明する手順を実行する前に確認します。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]コンピューターにインストールされます。  
  
- SQL Server Business Intelligence Development Studio は、コンピューターにインストールされます。  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートします。  
 使用して Siebel システムからデータをインポートする次の手順に従います[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]SQL Server Management Studio を使用します。  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートするには  
  
1. SQL Server Management Studio を起動します。  
  
2. **サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し、をクリックし、値を指定します。 **Connect**します。 Microsoft SQL Server Management Studio を開きます。  
  
3. オブジェクト エクスプ ローラーで、SQL Server 名を展開し、**データベース**をエクスポートするテーブル、Siebel システムからデータベースを右クリックします。 コンテキスト メニューをポイント**タスク**、 をクリックし、**データのインポート**します。 これは、SQL Server インポートおよびエクスポート ウィザードを起動します。  
  
4. クリックして、ようこそ画面の情報を読み取る**次**します。  
  
5. **データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リストで、 **Siebel eBusiness Applications の .NET Framework Data Provider**します。 さまざまな接続のプロパティの値を指定、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]接続文字列。 接続文字列プロパティの詳細については、次を参照してください。 [Siebel 接続文字列のデータ プロバイダー プロパティ](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)します。  
  
    **[次へ]** をクリックします。  
  
6. **変換先の選択** ダイアログ ボックス。  
  
   1.  **先**ドロップダウン リストで、 **SQL Native Client**します。  
  
   2.  **サーバー名**ドロップダウン リストで、SQL Server 名を選択します。  
  
   3.  認証モードを選択します。  
  
   4.  **データベース**ドロップダウン リストで、Siebel テーブルをインポートするデータベースを選択します。  
  
   5.  **[次へ]** をクリックします。  
  
7. **指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプション。  
  
8. **ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を参照してください[Siebel の SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)します。  
  
    をクリックして、**解析**クエリを検証します をクリックするボタン**OK**でクリックしてポップアップ ダイアログ ボックスで、 **次へ**。  
  
9. **選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。 ソースは、Siebel からデータを取得する指定したクエリです。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
10. ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更するには、クリックして**マッピングの編集**します。  
  
     ![Siebel および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")  
  
11. **列マッピング** ダイアログ ボックスができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブルで特定の列を無視します。  
  
    -   変換先テーブル内のフィールドのデータ型を変更します。  
  
    -   Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。  
  
         終了したら **[OK]** をクリックします。  
  
12. **選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。  
  
13. **実行パッケージの保存および** ダイアログ ボックス。  
  
    - 選択、**をすぐに実行**クエリを実行する チェック ボックス。  
  
    - 選択、 **SSIS パッケージの保存**パッケージとしてクエリが保存され、後で実行する チェック ボックス。 パッケージを保存する場合は、SQL Server またはファイル システムにパッケージを保存するかどうかも指定する必要があります。  
  
    - **パッケージの保護レベル**ドロップダウン リスト、選択、保護、パッケージのレベルし、資格情報を指定が必要です。  
  
    - **[次へ]** をクリックします。  
  
      パッケージを保存することを選択した場合は、次の手順に進みます。 それ以外の場合、手順 15 に進みます。  
  
14. **SSIS パッケージの保存** ダイアログ ボックスで、次を指定します。  
  
    -   パッケージの名前  
  
    -   パッケージの説明  
  
    -   SQL Server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。  
  
    -   ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。  
  
         終了したら **[次へ]** をクリックします。  
  
15. **ウィザードを完了**] ダイアログ ボックスで、ウィザードを実行し、[アクションの概要を確認**完了**します。  
  
16. **操作の実行**Siebel から SQL Server データベースのテーブルに情報をインポートするタスクの実行 ダイアログ ボックスで、ウィザードが起動します。 ウィザードでは、各タスクの状態が表示されます。  
  
17. すべてのタスクが正常に実行される、クリックして**閉じる**します。 タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 SSIS パッケージを保存する場合は、Siebel システムの最新の情報を取得することを行うことができます。 このセクションでは、ファイル システムに保存した場合は、パッケージを実行する方法について説明します。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>Windows エクスプ ローラーからパッケージを実行するには  
  
1. **Windows エクスプ ローラー**パッケージを保存した場所に移動して、パッケージをダブルクリックします。  
  
2. **[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[実行]** をクリックします。 **パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。  
  
3. すべてのタスクが正常に実行される、クリックして**閉じる**します。  
  
4. **[パッケージ実行ユーティリティ]** ダイアログ ボックスで **[閉じる]** をクリックします。  
  
   パッケージの実行に関する詳細については、パッケージの実行」を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)します。 いずれか、SSIS パッケージに関連するその他の情報を参照してください"パッケージ方法に関するトピック (SSIS)"で[ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行した後は、Siebel データをインポートする SQL Server データベースに移動して結果を確認する必要があります。 パッケージを実行する必要がありますのテーブルを作成、転送先データベース。 このテーブル Siebel テーブルから値を持つデータを設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [Data Provider for Siebel を SSIS と一緒に使用する](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)