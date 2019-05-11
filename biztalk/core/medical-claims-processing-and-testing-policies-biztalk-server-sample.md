---
title: Medical Claims Processing and Testing Policies (BizTalk Server サンプル) |Microsoft Docs
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
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5108e5d26b7da7761285c8b8e7ec1bde8deaf00c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325564"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a>Medical Claims Processing and Testing Policies (BizTalk Server サンプル)
Medical Claims Processing and Testing Policies サンプルでは、データベース テーブルと、受信ドキュメントから派生したファクトを検証して、これを使用して複数のルールを含んだ規則セットを作成する方法を示します。処理要求の結果を記録する NET ベースのオブジェクト。  
  
 このサンプルでは、単純なを使用して請求処理シナリオのエンド ツー エンドの実行を示します。要求の状態および状態の理由を確認する入力方向の要求に対して医療費請求ルールを実行するビジネス ルール エンジンを使用する NET ベースのアプリケーション。  
  
> [!NOTE]
>  このサンプルでは、デバッグ トレース ファイルを使用してビジネス ルール エンジン実行をトレースする方法も示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、送信された要求に、次の一連の規則が適用されます。  
  
1.  要求の合計量が、ポリシーによって許可された最大値を超えた場合、請求を拒否します。  
  
2.  場合、クライアントが病院で、ポリシーによって許可された最大値よりも詳細の夜、請求を拒否します。  
  
3.  要求の日付が、将来の場合、請求を拒否します。  
  
4.  ポリシーが有効でない場合は、要求を拒否します。  
  
5.  ポリシーの有効期限が切れている場合は、潜在顧客がポリシー ID および患者名と共にセールス部門に送信します。  
  
6.  それ以外の場合、要求を承認します。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Create_PolicyValidity_Table.sql|新しいテーブルを追加する SQL スクリプトでは、Northwind サンプル データベースに PolicyValidity という名前です。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\Claims フォルダー。<br /><br /> AssemblyInfo.cs、Claims.csproj、Claims.sln、Claims.cs|プロジェクト、ソリューション、ソース、および、請求処理の結果を記録するこのサンプルの部分に関連するファイルと呼ばれる、**し**ルールの一部です。|  
|\FactRetrieverForClaimsProcessing フォルダー。<br /><br /> AssemblyInfo.cs、FactRetrieverForClaimsProcessing.cs、FactRetrieverForClaimsProcessing.csproj、FactRetrieverForClaimsProcessing.sln|プロジェクト、ソリューション、ソース、およびこのサンプルで作成される PolicyValidity テーブルから情報を取得する長期間のファクト取得コンポーネントを提供するこのサンプルの部分に関連するファイル。|  
|\RulesForMedicalClaims フォルダー。<br /><br /> App.ico、AssemblyInfo.cs、RulesForMedicalClaims.cs、RulesForMedicalClaims.csproj、RulesForMedicalClaims.sln|プロジェクト、ソリューション、ソース、および他の関連ファイル (RulesForMedicalClaims.exe)、このサンプルとのメイン実行可能ファイルをプログラムで構成するこのサンプルの一部を定義しルール セットが格納されて、サンプルのファクトの構築および実行し、規則セットを使用して、 **PolicyTester**オブジェクト。|  
|\RulesForMedicalClaims フォルダー。<br /><br /> MedicalClaims.xsd|このサンプルに送信されるサンプル医療費請求の構造を定義するスキーマ ファイルです。|  
|\RulesForMedicalClaims フォルダー。<br /><br /> sampleClaim.xml|MedicalClaims.xsd ファイルで定義されているスキーマに準拠しているサンプル入力ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a>ビルドして初期化 Medical Claims Processing and Testing Policies サンプル  
  
1. コンピューターに Northwind データベースがあることを確認します。  
  
   > [!IMPORTANT]
   >  このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。 [ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。 
  
2. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing  
  
3. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - コンパイルし、展開、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Claims.dll、FactRetrieverForClaimsProcessing.dll、および RulesForMedicalClaims.dll を含む、このサンプルのプロジェクト。  
  
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
   > 
   > [!NOTE]
   >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
   - 指定された SQL の実行 SQL クエリ アナライザーを使用して、create_policyvalidity_table.sql という付属のスクリプトを作成します。 スクリプトでは、Northwind サンプル データベース内の 2 つのサンプル行と、PolicyValidity テーブルを作成します。 このテーブルは、2 つの列を持っています。ID および PolicyStatus します。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。  
  
   - 受信場所を有効にし、送信ポートを開始します。  
  
   - オーケストレーションを参加させ、開始します。  
  
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a>Medical Claims Processing and Testing Policies サンプルを実行するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\RulesForMedicalClaims\bin\Debug\ を Testing  
  
2. コマンドラインで RulesForMedicalClaims.exe ファイルを実行します。  
  
   > [!NOTE]
   >  サンプルの請求ファイル sampleClaim.xml の個々 の要素の値を変更し、サンプルを繰り返し実行できます。 これらの要素で別の値に対する想定される出力は、次の一覧に表示されます。  
  
   送信されたサンプル請求ファイル内の値のさまざまな組み合わせに基づいた出力シナリオは次のとおりです。  
  
-   額が $1000 を超える要求を次の出力が得られます。  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   宿泊数が 10 を超える要求を次の出力が得られます。  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   日付が有効でない要求 (日付 > 現在の日付)、次の出力が取得します。  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   無効なポリシー ID を持つクレームの (など、変更することで、 **ID**要素に値 2) ポリシーの有効期限のために次の出力が得られます。  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   有効な要求を次の出力が得られます。  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  テキスト ファイル、outputtrace.txt というこのサンプルを実行するたびに、フォルダーの ...\RulesForMedicalClaims\bin\Debug フォルダーに作成されます。 、ルール実行のデバッグ トレースが含まれていると、フォルダー \RulesForMedicalClaims\bin\Debug 下の各実行サイクルの後に作成されます。 ルールの実行の出力のトレースを表示するには、このファイルを調べることができます。  
  
## <a name="comments"></a>コメント  
 規則セットの評価で使用されるファクト ソースは次のとおりです。  
  
- 長期的なファクト取得コンポーネントをします。実装する NET ベースのアプリケーション、 **IFactReriever**インターフェイスでは、FactRetrieverForClaimsProcessing フォルダ内に構築されています。 PolicyValidity データベースから (データセットの形式) でデータを取得、ルール条件の評価で使用して、medical claims processing ポリシーによって使用されます。  
  
- クレームは、兄弟要素に格納されている、次の情報を含む XML ドキュメントの形式では。名前、ID、額、泊数、および日付。  
  
- A。NET ベースのクラス ライブラリ (Claims) は、使用、 **ClaimResults** (ポリシーが有効でない場合) は、潜在顧客を送信して、状態と、プロパティを使用して、要求の理由を記録するクラスが使用を呼び出すことによって、 **SendLeads**ID とパラメーターとして名前を持つメソッド。  
  
  これらのファクト ソースに基づいて、次のように、このシナリオで定義されたルールに説明できます。  
  
1. 入力方向の要求が有効かどうかを確認します。 量は、クレームの許容される制限を超えるポリシーが (データベース テーブルを調べて確認済み)、期限切れの場合の夜の数が許容される最大を超えたかどうかし、将来の日付、要求が行われた場合、要求が無効です。 要求が無効であると特定された場合、状態と要求の理由を適切に設定します。  
  
2. 入力方向の要求のポリシー ID の有効期限が切れている場合 (ポリシー ID および患者名) に潜在顧客をポリシー更新部門に送信します。  
  
3. 要求が有効な場合、状態と要求の理由を適切に設定します。  
  
   規則とその用語バインドのより形式的に表現は次のとおりです。  
  
-   **ルール 1。チェックの量**  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **規則 2 です。病院に費やされた夜間**  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **規則 3 です。日付の有効性**  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **規則 4 です。ポリシーの有効性**  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   **ルール 5。潜在顧客**  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   **ルール 6。請求の受理**  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール (BizTalk Server サンプル フォルダー)](../core/business-rules-biztalk-server-samples-folder.md)