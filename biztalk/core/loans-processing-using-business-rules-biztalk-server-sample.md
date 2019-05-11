---
title: Loans Processing Using Business Rules (BizTalk Server サンプル) |Microsoft Docs
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
ms.openlocfilehash: b8b878b782c49f1fc4827577444b8bffbec346fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380618"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a>Loans Processing Using Business Rules (BizTalk Server サンプル)
Loans Processing Using Business Rules サンプルでは、ファクトと呼ばれる入力の組み合わせを使用して、処理中のドキュメント内のフィールドの設定を計算する方法と、オーケストレーション内で管理しているルール セットを使用する方法を示します。 ファクトは呼び出しの結果であることができます、します。NET ベースのアセンブリ、メッセージの XML から取得した値またはデータベースからデータを取得します。 このサンプルでは、どのルールを変更できます、いつでもでも再デプロイすることがなく、後続の計算に影響を与えるも示します。  

## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、簡単なローン処理のシナリオのコンテキスト内でこれらの機能を示します。 BizTalk Server オーケストレーションは、ピックアップし、XML メッセージ形式、ローン ケースとも呼ばれますのローン申請を処理します。 このオーケストレーションは、規則の適用の結果とメッセージの変更と、出力フォルダーにファイルとして、メッセージを書き込み、規則に従って受信メッセージを評価するのにビジネス ルール エンジンを使用します。  

 このサンプルの設定の処理中のメッセージを含む複数のソースからのファクトに基づいた、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**処理中のメッセージの要素。  

## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Business Rules\Loans ビジネス Rules\ を使用した処理  

 次の表は、このサンプルのファイルとその目的を示しています。  


|                                                                                    ファイル                                                                                    |                                                                                                                説明                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                   Case.xsd                                                                                    |                                                                                 受信ローン申請、ローン ケースとも呼ばれるスキーマ ファイルです。                                                                                  |
|                                                                                  Cleanup.bat                                                                                  |                   アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。                   |
|                                                                           Create_CustInfo_Table.sql                                                                           |                                                                              SQL Northwind サンプル データベースに CustInfo テーブルを作成するための SQL スクリプトです。                                                                              |
|                                                                           LoanProcessorBinding.xml                                                                            |                                                                                               ポートのバインドなど、自動化されたセットアップに使用されます。                                                                                               |
|                                                                   LoansProcessor.btproj, LoansProcessor.sln                                                                   |                                                                                            このサンプルの BizTalk プロジェクトおよびソリューション ファイル。                                                                                             |
|                                                                             マイ サンプル Service.odx                                                                             |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] このサンプルのオーケストレーションです。                                                              |
|                                                                                sampleLoan.xml                                                                                 |                                                               サンプル入力ファイル、ファイルの XML 構造の末尾に次の 4 つの状態要素の空の値です。                                                               |
|                                                                                   Setup.bat                                                                                   |                                                                                                 このサンプルをビルドおよび初期化するために使用されます。                                                                                                  |
|         \CreateRules フォルダー。<br /><br /> App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs          | VisualC#プロジェクト、ソリューション、ソース、および関連ファイルをプログラムで、セット内の規則を作成するアプリケーションを作成するために使用します。 一連の規則をプログラムで構築するための例については、ソース ファイル WriteToBRL.cs を参照してください。 |
| \MyFactRetriever フォルダー。<br /><br /> AssemblyInfo.cs<br /><br /> FactRetrieverForLoansProcessing.cs<br /><br /> myFactRetriever.csproj<br /><br /> myFactRetriever.sln |                 VisualC#プロジェクト、ソリューション、ソース、および関連ファイルを使用して、先ほど追加した Northwind サンプルの SQL Server データベースに CustInfo テーブルから情報を取得するアセンブリを作成するために使用します。                  |

## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  

#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a>ビルドして初期化 Loans Processing Using Business Rules サンプル  

1. コンピューターに Northwind データベースがあることを確認します。  

   > [!IMPORTANT]
   >  このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。 [ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。 

2. コマンド ウィンドウで、次のフォルダーに移動します。  

    \<*パスのサンプル*\>\Business Rules\Loans Processing using Business Rules  

3. ファイルは、次の操作を実行します。 Setup.bat を実行します。  

   - このサンプルの以前の実行からときに残ったデータを排除する GAC をクリーンアップします。  

   - コンパイルし、展開、ファクト取得プログラム myFactRetreiever.dll します。  

   - SQL スクリプト ファイル Create_CustInfo_Table.sql を使用して、Northwind サンプル SQL データベースに CustInfo という名前のテーブルを追加します。  

   - このサンプルの以前の実行のときに残ったに共有 SQL ルール ストアをクリーンアップします。  

   - 作成、公開、され、ローン処理ルール セットの最新バージョン (1.0) をデプロイします。  

     > [!NOTE]
     >  ツールに付属しているビジネス ルール作成ツールを使用する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をプログラムで設定されているルールを確認します。  

   - 入力 (In) フォルダと出力 (Out) フォルダこのサンプルを作成します。  

   - コンパイルし、残りの展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]このサンプルでは、このサンプルを調整するために使用するオーケストレーションを含む BizTalk プロジェクトを含むプロジェクト。  

   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の受信場所、送信ポート、および受信ポートを作成しバインドします。  

     > [!NOTE]
     >  このサンプルでは、作成してポートをバインドする場合は、次の警告が表示されます。  
     >   
     >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
     >   
     >  これらの警告は、無視してもかまいません  (インストールでの名前付け方法はユーザーによって異なる可能性があるため、ホスト名と受信ハンドラーはバインド ファイルから除外されています。)  

   - 受信場所を有効にし、送信ポートを開始します。  

   - 参加させ、オーケストレーションを開始します。  

> [!NOTE]
>  BizTalk ホスト名が BizTalkServerApplication でない場合は、Setup.bat ファイルおよび LoanProcessorBinding.xml 適切なホスト名を反映するようにファイルを変更します。  
> 
> [!NOTE]
>  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
> 
> [!NOTE]
>  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
> 
> [!NOTE]
>  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  

## <a name="running-this-sample"></a>このサンプルの実行  

#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a>Loans Processing Using Business Rules サンプルを実行するには  

1. ファイル sampleLoan.xml のコピー、 **\In**フォルダー。  

2. フォルダーに作成した .xml ファイルを観察**アウト**します。データが XML 構造の末尾に次の 4 つの状態要素に追加の入力 XML メッセージが含まれています。**IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。  

   規則セット内のルールを変更するビジネス ルール作成ツールを使用し、それらのルールを再デプロイできます。  

#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a>ビジネス ルール作成ツールを使用して、1 つ以上の規則セット内のルールを変更するには  

1. クリックして**開始**、 をポイント**プログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。  

   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。 これを行うには、アプリケーションを右クリックし、**管理者として実行**します。  

2. **SQL Server**ダイアログ ボックスで、をクリックして **[ok]** ルール ストアに接続します。  

3. **ポリシー エクスプ ローラー**、ノードの下**LoanProcessing**を右クリックし、**バージョン 1.0-展開済み**ノード、およびクリック**コピー**します。  

4. 右クリック**LoanProcessing**、 をクリックし、**貼り付け**します。  

5. ルールまたはさまざまな値の原因となる方法で処理を変更、 **IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**要素。 否定部分の値を変更することを確認します (基本的には、 **Else**句) ルールを変更するのです。  

    次の表では、このサンプルで使用される規則のセットを示します。 特に断り、しない限り、ファクトは受信 XML メッセージです。 文字列 (db) では、ファクトのソースとしてデータベースを示します。  


   |  規則番号   |        ルール名        |                                                                             説明                                                                             |
   |----------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       1        |   収入状態ルール    |                                       IF **BasicSalary** + **OtherIncome** > 0<br /><br /> **IncomeStatus** = **有効**                                        |
   |       2        | 契約状態ルール | IF **ID** == **ID (db)**<br /><br /> AND<br /><br /> IF **CreditCardBalance (db)** > 500<br /><br /> THEN **CommitmentsStatus** =<br /><br /> 「コンピューティング コミットメント」 |
   |       3        | 雇用状態ルール  |                                  IF **EmploymentType &#124; TimeInMonths** > 18<br /><br /> **EmploymentStatus** = **有効**                                   |
   |       4        |  常駐状態ルール  |                                  IF **PlaceOfResidence &#124; TimeInMonths** > 18<br /><br /> **ResidencyStatus** = **有効**                                  |
   | !1, !2, !3, !4 |     否定ルール      |    論理の条件**いない**のルール 1 ~ 4 で説明されている対応する条件。 結果が設定される文字列に変わります。     |


6. 右クリックし、**バージョン 1.1 (未保存)** ノード、およびクリック**保存**します。  

7. 右クリックし、**バージョン 1.1**ノード、およびクリック**発行**します。  

8. 右クリックし、**バージョン 1.1**ノード、およびクリック**デプロイ**します。  

9. 共有の SQL Server ルール ストアに反映されるまで、変更の 60 秒間待機します。  

10. ファイル sampleLoan.xml のコピーをフォルダーに貼り付ける**で**します。  

11. フォルダーに作成した .xml ファイルを観察**アウト**します。データが XML 構造の末尾に次の 4 つの状態要素に追加の入力 XML メッセージが含まれています。**IncomeStatus**、 **CommitmentsStatus**、 **EmploymentStatus**、および**ResidencyStatus**します。 これらの要素に追加されたデータは異なります、またはそうでない、前の手順 5. でこの手順で行われた変更の種類に基づいて、実行します。  

## <a name="comments"></a>コメント  
 このサンプルの追跡情報を表示する場合は、解除して、ビジネス ルール エンジン展開ウィザードを使用して、関連するルールのセット (Loans Processing) を再デプロイする必要があります。  

 このサンプルでは、ビジネス ルールを使用して、オーケストレーション内のルールの形式でビジネス ポリシーを適用する方法を示します。 また、ポリシーを変更し、再コンパイルやオーケストレーション ソリューションを再デプロイしなくても、オーケストレーション内で動的に反映されるポリシーに変更がある方法を示します。  

 このサンプルの入力ローン ケースは、次の構造を持つ XML メッセージです。  

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