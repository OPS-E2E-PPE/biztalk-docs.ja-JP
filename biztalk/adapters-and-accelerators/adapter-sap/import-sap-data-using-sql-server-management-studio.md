---
title: SQL Server Management Studio を使用して SAP のデータのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6c825653321f2dbe0bf5ef1f5ed58676e6ae90e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995683"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a>SQL Server Management Studio を使用して SAP データのインポート
このセクションでは、SAP システムから SQL Server データベースにデータをインポートする、SQL Server Management Studio を使用する方法について説明します。 このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の手順を説明します。 このセクションでは、SSIS パッケージを実行する方法に関する情報も提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明する手順を実行する前に確認します。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] コンピューターにインストールされます。  
  
- SQL Server Business Intelligence Development Studio は、コンピューターにインストールされます。  
  
### <a name="to-import-data-using-sql-server-management-studio"></a>SQL Server Management Studio を使用してデータをインポートするには  
  
1. SQL Server Management Studio を起動します。  
  
2. **サーバーへの接続** ダイアログ ボックスで、SQL Server データベースに接続し をクリックして値を指定**Connect**します。 **Microsoft SQL Server Management Studio**が開きます。  
  
3. **オブジェクト エクスプ ローラー**展開し、SQL Server 名を展開し、**データベース**をエクスポートするテーブルの SAP システムからデータベースを右クリックします。 コンテキスト メニューをポイント**タスク**、 をクリック**データのインポート**します。 起動、 **SQL Server インポートおよびエクスポート ウィザード**します。  
  
4. クリックして [ようこそ] 画面の情報を読み取る**次**します。  
  
5. **データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**mySAP Business Suite の .NET Framework Data Provider**します。 ダイアログ ボックスでは、SAP システムへの接続に別の接続パラメーターが一覧表示します。 SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
   - 接続の種類の接続パラメーター。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。 たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。  
  
   - ユーザー名とパスワードなどの SAP システムに接続するログイン情報。  
  
     SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーについて](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
     **データ ソースの選択** ダイアログ ボックスで指定します。  
  
   - 任意の 1 つの接続の接続パラメーターを入力します。  
  
   - SAP システムへの接続にログイン情報。  
  
   - SAP GUI のデバッグを有効にするかどうか。  
  
   - RFC SDK トレースを使用するかどうか。  
  
     **[次へ]** をクリックします。  
  
6. **変換先の選択** ダイアログ ボックス。  
  
   1.  **先**ドロップダウン リストで、 **SQL Native Client**します。  
  
   2.  **サーバー名**ドロップダウン リストで、SQL server の名前を選択します。  
  
   3.  認証モードを選択します。  
  
   4.  **データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。  
  
   5.  **[次へ]** をクリックします。  
  
7. **指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションを選択し、をクリックして**次**します。  
  
8. **ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[選択ステートメント SAP の構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。  
  
    をクリックして、**解析** をクリックしてクエリを検証します をクリックして**OK**ポップアップ ダイアログ ボックスで。 **[次へ]** をクリックします。  
  
9. **選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。 ソースは、SAP からデータを取得する指定したクエリです。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
10. ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更するには、クリックして**マッピングの編集**します。  
  
     ![SAP および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
11. **列マッピング** ダイアログ ボックスができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブルで特定の列を無視します。  
  
    -   変換先テーブル内のフィールドのデータ型を変更します。  
  
    -   Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。  
  
    -   **[OK]** をクリックします。  
  
12. **選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。  
  
13. **実行パッケージの保存および**ダイアログ ボックスで、  
  
    - 選択、**をすぐに実行**クエリを実行する チェック ボックス。  
  
    - 選択、 **SSIS パッケージの保存**パッケージとしてクエリが保存され、後で実行する チェック ボックス。 パッケージを保存する場合は、SQL Server またはファイル システムにパッケージを保存するかどうかも指定する必要があります。  
  
    - **パッケージの保護レベル**ドロップダウン リスト、選択、保護、パッケージのレベルし、資格情報を指定が必要です。  
  
    - **[次へ]** をクリックします。  
  
      パッケージを保存することを選択した場合は、次の手順に進みます。 それ以外の場合、手順 15 に進みます。  
  
14. **SSIS パッケージの保存** ダイアログ ボックスで指定します。  
  
    -   パッケージの名前  
  
    -   パッケージの説明  
  
    -   SQL server にパッケージを保存する場合は、選択から SQL Server、**サーバー名**ドロップダウン リスト。  
  
    -   ファイル システムにパッケージを保存する場合は、指定のファイルの場所と名前、**ファイル名**テキスト ボックス。  
  
    -   **[次へ]** をクリックします。  
  
15. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**します。  
  
16. **操作の実行**SAP から情報を SQL Server データベースのテーブルにインポートするタスクを実行するダイアログ ボックスで、ウィザードを起動します。 ウィザードでは、各タスクの状態が表示されます。  
  
17. すべてのタスクが正常に実行される、クリックして**閉じる**します。 タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 SSIS パッケージを保存する場合を実行すると、SAP システムから最新の情報を取得できます。 このセクションでは、ファイル システムに保存した場合に、パッケージを実行する方法について説明します。  
  
#### <a name="to-run-the-package-from-windows-explorer"></a>Windows エクスプ ローラーからパッケージを実行するには  
  
1. **Windows エクスプ ローラー**パッケージを保存した場所に移動して、パッケージをダブルクリックします。  
  
2. **パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**Execute**します。  
  
3. **パッケージ実行の進行状況** ダイアログ ボックスには、さまざまなタスクの進行状況が表示されます。  
  
4. すべてのタスクが正常に実行される、クリックして**閉じる**します。  
  
5. **パッケージ実行ユーティリティ**ダイアログ ボックスで、をクリックして**閉じる**します。  
  
   パッケージの実行の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)します。 SSIS パッケージに関連するその他の情報を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行した後は、SAP のデータをインポートする SQL Server データベースに移動して結果を確認する必要があります。 パッケージを実行する必要がありますが転送先データベースでテーブルを作成し、SAP テーブルから値が格納されます。  
  
## <a name="see-also"></a>参照  
 [Data Provider for SAP を SSIS と一緒にの使用](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)