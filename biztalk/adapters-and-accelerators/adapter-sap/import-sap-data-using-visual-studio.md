---
title: Visual Studio を使用して SAP のデータのインポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 700d597b3532c0034623553a6d1f0f8147e5642d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986003"
---
# <a name="import-sap-data-using-visual-studio"></a>Visual Studio を使用した SAP データのインポート
このセクションでは、Microsoft を使用する方法の情報を提供します[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]SAP システムから SQL Server データベースにデータをインポートします。 このセクションでは、データをインポートする実行可能な SSIS パッケージを作成する方法の手順を説明します。 このセクションでは、SSIS パッケージを実行する方法に関する情報も提供します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックで説明する手順を実行する前に確認します。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] コンピューターにインストールされます。  
  
- [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] コンピューターにインストールされます。  
  
### <a name="to-import-data-using-visual-studio"></a>Visual Studio を使用してデータをインポートするには  
  
1. 開始[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]との統合サービス プロジェクトを作成します。  
  
2. **プロジェクト**メニューの  **SSIS インポートおよびエクスポート ウィザード**します。 起動、 **SQL Server インポートおよびエクスポート ウィザード**します。  
  
3. クリックして [ようこそ] 画面の情報を読み取る**次**します。  
  
4. **データ ソースの選択** ダイアログ ボックスから、**データ ソース**ドロップダウン リスト**mySAP Business Suite の .NET Framework Data Provider**します。 ダイアログ ボックスでは、SAP システムへの接続に別の接続パラメーターが一覧表示します。 SAP システムを使用して接続するための一般的な接続文字列、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]が必要です。  
  
   - 接続の種類の接続パラメーター。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] A、B、および D の接続の種類をサポートしていますSAP システムへの接続には、いずれかの接続パラメーターを指定する必要があります*1 つ*のこれらの接続の種類。 たとえば、A の接続の種類、アプリケーション サーバーのホストとシステムの数の名前を指定する必要があります。  
  
   - ユーザー名とパスワードなどの SAP システムに接続するログイン情報。  
  
     SAP システムを使用して接続する接続文字列の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP 接続文字列のデータ プロバイダーについて](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)します。  
  
     **データ ソースの選択** ダイアログ ボックスで指定します。  
  
   - 任意の 1 つの接続の接続パラメーターを入力します。  
  
   - SAP システムへの接続にログイン情報。  
  
   - SAP GUI のデバッグを有効にするかどうか。  
  
   - RFC SDK トレースを使用するかどうか。  
  
     **[次へ]** をクリックします。  
  
5. **変換先の選択** ダイアログ ボックス。  
  
   1.  **先**ドロップダウン リストで、 **SQL Native Client**します。  
  
   2.  **サーバー名**ドロップダウン リストで、SQL server の名前を選択します。  
  
   3.  認証モードを選択します。  
  
   4.  **データベース**ドロップダウン リストで、SAP テーブルをインポートするデータベースを選択します。  
  
   5.  **[次へ]** をクリックします。  
  
6. **指定のテーブルのコピーまたはクエリ** ダイアログ ボックスで、選択、**を転送するデータを指定するクエリを記述**オプションを選択し、をクリックして**次**します。  
  
7. **ソース クエリの指定** ダイアログ ボックスで、SQL Server にインポートするデータをフィルター選択クエリを指定します。 クエリの SELECT、文法の詳細については、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を参照してください[SAP で SELECT ステートメントの構文](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)します。  
  
    をクリックして、**解析** をクリックしてクエリを検証します をクリックして**OK**ポップアップ ダイアログ ボックスで。 **[次へ]** をクリックします。  
  
8. **選択元のテーブルおよびビュー**  ダイアログ ボックスで、ソースと変換先のテーブルに対してチェック ボックスをオンにします。 ソースは、SAP からデータを取得する指定したクエリです。 変換先は、SQL Server データベースに作成されるテーブルです。  
  
9. ウィザードは、ソースと宛先の間の既定のマッピング テーブルのフィールドを作成します。 ただし、要件に従って、マッピングを変更することができます。 フィールド マッピングを変更するには、クリックして**マッピングの編集**します。  
  
     ![SAP および SQL テーブル間の列マッピング](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")  
  
10. **列マッピング** ダイアログ ボックスができます。  
  
    -   変換先テーブル内の列の名前を変更します。  
  
    -   変換先テーブルで特定の列を無視します。  
  
    -   変換先テーブル内のフィールドのデータ型を変更します。  
  
    -   Null 許容型のサイズ、有効桁数、およびスケールなどの他のフィールドの属性を変更します。  
  
    -   **[OK]** をクリックします。  
  
11. **選択元のテーブルおよびビュー**ダイアログ ボックスで、をクリックして**次**。  
  
12. **ウィザードを完了** ダイアログ ボックスで、ウィザードを実行し、をクリックする操作の概要を確認**完了**します。  
  
13. **操作を実行して**SAP から情報を SQL Server データベースのテーブルにインポートするタスクを実行するダイアログ ボックスで、ウィザードを起動します。 ウィザードでは、各タスクの状態が表示されます。  
  
14. すべてのタスクが正常に実行される、クリックして**閉じる**します。 タスクが失敗した場合、対応するエラー メッセージが表示、問題を解決し、ウィザードを再実行します。  
  
15. ウィザードでは、統合サービス プロジェクトに、SSIS パッケージを追加します。 統合サービス プロジェクトを保存します。  
  
## <a name="running-the-ssis-package"></a>SSIS パッケージを実行します。  
 統合サービス プロジェクトでは、パッケージが作成されると、SAP システムから SQL Server データベースにデータをインポートすることを実行できます。 パッケージを実行して SAP データをインポートするのには、次の手順を実行します。  
  
#### <a name="to-run-the-package-from-visual-studio"></a>Visual Studio からパッケージを実行するには  
  
1. ソリューション エクスプ ローラーで SSIS パッケージに移動します。  
  
2. パッケージ名を右クリックして**パッケージ実行**します。  
  
   パッケージの実行の詳細については、次を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)します。 SSIS パッケージに関連するその他の情報を参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)します。  
  
## <a name="verifying-the-results"></a>結果の確認  
 パッケージを実行した後は、SQL Server にログオンしている、SAP データをインポートするデータベースに移動して結果を確認する必要があります。 パッケージを実行する必要がありますが転送先データベースでテーブルを作成し、SAP テーブルから値が格納されます。  
  
## <a name="see-also"></a>参照  
 [Data Provider for SAP を SSIS と一緒に使用する](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)