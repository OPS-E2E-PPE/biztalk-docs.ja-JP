---
title: Loans Processing Using Business Rules (BizTalk Server サンプル) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82476c440f1bae482eff5308f1a5238f8bd85d92
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008347"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a>ローン処理を使用してビジネス ルール (BizTalk Server サンプル)
Loans Processing Using Business Rules サンプルは、オーケストレーション内で管理しているルール セットを使用する方法、および入力 (ファクトと呼ばれます) の組み合わせを使用して、処理中のドキュメント内のフィールドの設定値を計算する方法を示しています。 ファクトは、.NET ベースのアセンブリ呼び出しの結果、メッセージの XML から取得した値、またはデータベースから取得したデータです。 このサンプルでは、ルールを必要に応じて変更して、再展開の必要なしに後続の計算に影響を与える方法も示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、簡単なローン処理のシナリオでこれらの機能を示します。 BizTalk Server オーケストレーションは、XML メッセージ形式のローン申請 (ローン ケースともいう) を取得して処理します。 このオーケストレーションでは、ビジネス ルール エンジンを使用してルールに従って受信メッセージを評価し、ルール適用の結果を使用してメッセージを変更し、メッセージをファイルとして出力フォルダーに書き込みます。  
  
 このサンプルの設定の処理中のメッセージをなど、いくつかのソースからのファクトに基づいた、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**処理中のメッセージの要素。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Business Rules\Loans ビジネス Rules\ を使用して処理  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Case.xsd|受信ローン申請 (ローン ケース) のスキーマ ファイルです。|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Create_CustInfo_Table.sql|SQL Northwind サンプル データベースの CustInfo テーブルを作成するための SQL スクリプトです。|  
|LoanProcessorBinding.xml|ポートのバインドなど、自動化されたセットアップに使用されます。|  
|LoansProcessor.btproj、LoansProcessor.sln|このサンプルの BizTalk プロジェクト ファイルとソリューション ファイルです。|  
|My Sample Service.odx|このサンプルの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションです。|  
|sampleLoan.xml|サンプルの入力ファイルです。ファイルの XML 構造の末尾で、4 つの状態要素の値が空になっています。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\CreateRules フォルダーには、次のファイルが含まれます。<br /><br /> App.ico、AssemblyInfo.cs、Case.xsd、CreateLoanProcessingPolicy.csproj、CreateLoanProcessingPolicy.sln、WriteToBRL.cs|プログラムによってセット内にルールを作成するアプリケーションを作成するために使う Visual C# プロジェクト、ソリューション、ソース、および関連ファイルです。 プログラムによってルール セットを作成する方法の例については、ソース ファイル WriteToBRL.cs を参照してください。|  
|\myFactRetriever フォルダーには、次のファイルが含まれます。<br /><br /> AssemblyInfo.cs<br /><br /> FactRetrieverForLoansProcessing.cs<br /><br /> myFactRetriever.csproj<br /><br /> myFactRetriever.sln|SQL Server のサンプルの Northwind データベースにあらかじめ追加された CustInfo テーブルからの情報の取得に使用するアセンブリを作成するために使う Visual C# プロジェクト、ソリューション、ソース、および関連ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a>Loans Processing Using Business Rules サンプルをビルドして初期化するには  
  
1.  コンピューターに Northwind データベースがインストールされていることを確認してください。  
  
    > [!IMPORTANT]
    >  このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。 [ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。 
  
2.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     \<*パスのサンプル*\>\Business Rules\Loans Processing using Business Rules  
  
3.  次の操作を実行する Setup.bat ファイルを実行します。  
  
    -   GAC をクリーンアップして、このサンプルを前回実行したときに残ったデータを削除します。  
  
    -   ファクト取得プログラム myFactRetreiever.dll をコンパイルし、展開します。  
  
    -   SQL スクリプト ファイル Create_CustInfo_Table.sql を使用して、Northwind サンプル SQL データベースに CustInfo という名前のテーブルを追加します。  
  
    -   共有 SQL ルール ストアをクリーンアップして、このサンプルを前回実行したときに残ったデータを削除します。  
  
    -   ローン処理ルール セットの最新バージョン (1.0) を作成、公開し、展開します。  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に用意されているビジネス ルール作成ツールを使用すると、プログラムによって設定されたルールを確認できます。  
  
    -   このサンプルで使用される入力 (In) フォルダーと出力 (Out) フォルダーを作成します。  
  
    -   このサンプルの残りの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト (このサンプルを調整するために使用するオーケストレーションが格納された BizTalk プロジェクトを含む) をコンパイルして展開します。  
  
    -   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  
  
        > [!NOTE]
        >  このサンプルでは、作成してポートをバインドするときに、次の警告が表示されます。  
        >   
        >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
        >   
        >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  
  
    -   受信場所を有効にし、送信ポートを開始します。  
  
    -   オーケストレーションを登録して開始します。  
  
> [!NOTE]
>  BizTalk ホスト名が BizTalkServerApplication でない場合は、適切なホスト名を反映するように Setup.bat ファイルおよび LoanProcessorBinding.xml ファイルを編集します。  
  
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
> [!NOTE]
>  開き、Setup.bat ファイルを実行せずにこのサンプルのプロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して、厳密な名前のキー ペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a>Loans Processing Using Business Rules サンプルを実行するには  
  
1.  ファイル sampleLoan.xml のコピーを貼り付け、 **\In**フォルダーです。  
  
2.  .Xml ファイル、フォルダーに作成を観察**アウト**です。XML データ構造の末尾に次の 4 つの状態要素に追加されたデータと、入力 XML メッセージが含まれています: **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**です。  
  
 ビジネス ルール作成ツールを使用してルール セット内のルールを変更し、変更されたルールを再展開できます。  
  
#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a>ビジネス ルール作成ツールを使用してルール セット内のルールを変更するには  
  
1.  をクリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**です。  
  
2.  **SQL Server**ダイアログ ボックスで、をクリックして**OK**ルール ストアへの接続にします。  
  
3.  **ポリシー エクスプ ローラー**、ノードの下に**LoanProcessing**を右クリックし、**バージョン 1.0-展開済み**ノードをクリックして**コピー**です。  
  
4.  右クリック**LoanProcessing**、クリックして**貼り付け**です。  
  
5.  ルールまたはに別の値の原因となるように処理を変更、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**要素。 否定部分の値を変更することを確認してください (基本的には、 **Else**句) ルールを変更するのです。  
  
     次の表に、このサンプルで使用されるルール セットを示します。 特に断りのない限り、ファクトは受信 XML メッセージから取得されます。 文字列 (db) は、ファクトのソースであるデータベースを表します。  
  
    |ルール番号|ルール名|Description|  
    |-----------------|---------------|-----------------|  
    |1|収入状態ルール|IF **BasicSalary** + **OtherIncome** > 0<br /><br /> **IncomeStatus** = **有効**|  
    |2|契約状態ルール|IF **ID** == **ID (db)**<br /><br /> [AND]<br /><br /> IF **CreditCardBalance (db)** > 500<br /><br />  **CommitmentsStatus** =<br /><br /> "Compute Commitments"|  
    |3|雇用状態ルール|IF **EmploymentType &#124;です。TimeInMonths** > 18<br /><br /> **EmploymentStatus** = **有効**|  
    |4|常駐状態ルール|IF **PlaceOfResidence &#124;です。TimeInMonths** > 18<br /><br /> **ResidencyStatus** = **有効**|  
    |!1, !2, !3, !4|否定ルール|論理条件**いない**ルール 1 ~ 4 で説明されている、対応する条件のです。 設定されている文字列の変更の結果として得られる操作には。|  
  
6.  右クリックし、**バージョン 1.1 (未保存)** ノードをクリックして**保存**です。  
  
7.  右クリックし、**バージョン 1.1**ノードをクリックして**発行**です。  
  
8.  右クリックし、**バージョン 1.1**ノードをクリックして**展開**です。  
  
9. 共有 SQL Server ルール ストアに変更が反映されるまで、60 秒間待機します。  
  
10. ファイル sampleLoan.xml のコピーをフォルダーに貼り付ける**で**です。  
  
11. .Xml ファイル、フォルダーに作成を観察**アウト**です。XML データ構造の末尾に次の 4 つの状態要素に追加されたデータと、入力 XML メッセージが含まれています: **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**です。 これらの要素に追加されたデータは、手順 5. で行った変更により、前回の実行結果とは異なります。  
  
## <a name="comments"></a>コメント  
 このサンプルの追跡情報を確認するには、ビジネス ルール エンジン展開ウィザードを使用して関連するルール セット (Loans Processing) をいったん展開解除し、再展開する必要があります。  
  
 このサンプルでは、ビジネス ルールを使用してオーケストレーション内のルールの形式でビジネス ポリシーを適用する方法を示しています。 ポリシーを変更し、このポリシーの変更を、オーケストレーション ソリューションを再コンパイルまたは再展開せずにオーケストレーション内で動的に反映する方法も示しています。  
  
 このサンプルへの入力ローン ケースは、次の構造の XML メッセージです。  
  
```  
    Name  
    ID  
    Income  
        BasicSalary  
        OtherIncome  
    EmploymentType  
        TimeInMonths  
    PlaceOfResidence  
        TimeInMonths  
    CommitmentsStatus  
    IncomeStatus  
    EmploymentStatus  
    ResidencyStatus  
```  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server サンプル フォルダー)](../core/business-rules-biztalk-server-samples-folder.md)