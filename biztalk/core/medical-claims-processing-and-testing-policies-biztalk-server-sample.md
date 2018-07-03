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
ms.openlocfilehash: 8e67b9a631764ed83659b05aa11f4c1570484f74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994867"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a>Medical Claims Processing and Testing Policies (BizTalk Server サンプル)
Medical Claims Processing and Testing Policies サンプルは、データベース テーブルおよび受信ドキュメントから派生したファクトを検証し、.NET ベースのオブジェクトを使用して請求処理の結果を記録する複数のルールを含むルール セットを作成する方法を示します。  
  
 このサンプルは、ビジネス ルール エンジンを使用して、受信した請求に対して医療費請求ルール セットを実行し、請求のステータスとそのステータスの理由を決定する .NET ベースのシンプルなアプリケーションを使用した請求処理シナリオのエンド ツー エンド実行を示します。  
  
> [!NOTE]
>  このサンプルは、デバッグ トレース ファイルを使用してビジネス ルール エンジンの実行を追跡する方法も示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、送信された請求に対して以下の順序でルールを適用します。  
  
1.  請求額がポリシーの最大限度額を超えている場合は、請求を拒否します。  
  
2.  患者の入院期間がポリシーの最長期間を超えている場合は、請求を拒否します。  
  
3.  請求日が将来の日付の場合は、請求を拒否します。  
  
4.  ポリシーが有効でない場合は、請求を拒否します。  
  
5.  ポリシーの有効期限が切れている場合は、情報がポリシー ID および患者名と共にセールス部門に送信されます。  
  
6.  上記以外の場合は、請求が承認されます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Cleanup.bat|アセンブリを展開解除し、グローバル アセンブリ キャッシュ (GAC) から削除するために使用されます。 送信ポートと受信ポートが削除されます。 必要に応じて、Microsoft インターネット インフォメーション サービス (IIS) の仮想ディレクトリが削除されます。|  
|Create_PolicyValidity_Table.sql|PolicyValidity という新しいテーブルを Northwind サンプル データベースに追加する SQL スクリプトです。|  
|Setup.bat|このサンプルをビルドおよび初期化するために使用されます。|  
|\Claims フォルダー内のファイル : <br /><br /> AssemblyInfo.cs、Claims.csproj、Claims.sln、Claims.cs|プロジェクト、ソリューション、ソース、および、請求処理の結果を記録するこのサンプルの部分に関連するファイルと呼ばれる、**し**ルールの一部です。|  
|\FactRetrieverForClaimsProcessing フォルダー内のファイル : <br /><br /> AssemblyInfo.cs、FactRetrieverForClaimsProcessing.cs、FactRetrieverForClaimsProcessing.csproj、FactRetrieverForClaimsProcessing.sln|このサンプルで、このサンプルによって作成される PolicyValidity テーブルから情報を取得する長期間のファクト取得コンポーネントを提供する部分のプロジェクト、ソリューション、ソース、および関連ファイルです。|  
|\RulesForMedicalClaims フォルダー内のファイル: <br /><br /> App.ico、AssemblyInfo.cs、RulesForMedicalClaims.cs、RulesForMedicalClaims.csproj、RulesForMedicalClaims.sln|プロジェクト、ソリューション、ソース、および他の関連ファイル (RulesForMedicalClaims.exe)、このサンプルとのメイン実行可能ファイルをプログラムで構成するこのサンプルの一部を定義しルール セットが格納されて、サンプルのファクトの構築および実行し、規則セットを使用して、 **PolicyTester**オブジェクト。|  
|\RulesForMedicalClaims フォルダー内のファイル: <br /><br /> MedicalClaims.xsd|このサンプルに送信されるサンプル医療費請求の構造を決定するスキーマ ファイルです。|  
|\RulesForMedicalClaims フォルダー内のファイル: <br /><br /> sampleClaim.xml|MedicalClaims.xsd ファイルで定義されているスキーマに準拠したサンプル入力ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a>Medical Claims Processing and Testing Policies サンプルをビルドして初期化するには  
  
1. コンピューターに Northwind データベースがインストールされていることを確認してください。  
  
   > [!IMPORTANT]
   >  このサンプルを実行するには、SQL Server の Northwind サンプル データベースが必要です。 [ダウンロード](https://www.microsoft.com/download/details.aspx?id=23654)、およびインストールします。 
  
2. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\ を Testing  
  
3. ファイルは、次の操作を実行します。 Setup.bat を実行します。  
  
   - このサンプルの [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクト (Claims.dll、FactRetrieverForClaimsProcessing.dll、および RulesForMedicalClaims.dll を含む) をコンパイルして展開します。  
  
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
   > 
   > [!NOTE]
   >  開き、Setup.bat ファイルを実行することがなくこのサンプルでは、プロジェクトをビルドする場合は、まず、.NET Framework の厳密名ユーティリティ (sn.exe) を使用して厳密な名前キーのペアを作成する必要があります。 このキー ペアは、生成されたアセンブリの署名に使用します。  
  
   - SQL Query Analyzer を使用して、Create_PolicyValidity_Table.sql という付属の SQL スクリプトを実行します。 このスクリプトによって、2 つのサンプル行を含む PolicyValidity というテーブルが Northwind サンプル データベースに作成されます。 このテーブルには、2 つの列 (ID および PolicyStatus) があります。  
  
   - [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の送信ポートおよび受信ポートを作成し、バインドします。  
  
   - 受信場所を有効にし、送信ポートを開始します。  
  
   - オーケストレーションを参加させ、開始します。  
  
   > [!NOTE]
   >  Setup.bat によって行われた変更を元に戻すには、Cleanup.bat を実行します。 Setup.bat を 2 回目に実行する場合は、その前に Cleanup.bat を実行してください。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a>Medical Claims Processing and Testing Policies サンプルを実行するには  
  
1. コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Business Rules\Medical Claims Processing and Policies\RulesForMedicalClaims\bin\Debug\ を Testing  
  
2. コマンド ラインで RulesForMedicalClaims.exe ファイルを実行します。  
  
   > [!NOTE]
   >  サンプル請求ファイル sampleClaim.xml の個々の要素の値を変更して、サンプルを繰り返し実行できます。 これらの要素の値が異なるいくつかのシナリオの予期される出力を次の表に示します。  
  
   送信されたサンプル請求ファイル内の値のさまざまな組み合わせによって得られる出力シナリオは次のとおりです。  
  
-   請求額が $1000 を超える場合、次の出力が得られます。  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   入院期間が 10 泊を超える請求の場合、次の出力が得られます。  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   日付が無効な請求の場合 (日付が現在の日付よりも先の場合)、次の出力が得られます。  
  
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
  
-   有効な請求の場合は、次の出力が得られます。  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  このサンプルを実行するたびに、outputtrace.txt というテキスト ファイルが ...\RulesForMedicalClaims\bin\Debug フォルダに作成されます。 このテキスト ファイルには、ルール実行のデバッグ トレースが含まれます。このファイルは、各実行サイクルの後に \RulesForMedicalClaims\bin\Debug フォルダに作成されます。 このファイルを参照して、ルール実行の出力トレースを確認できます。  
  
## <a name="comments"></a>コメント  
 ルール セットの評価に使用されるファクト ソースは次のとおりです。  
  
- 長期的なファクト取得コンポーネントをします。実装する NET ベースのアプリケーション、 **IFactReriever**インターフェイスでは、FactRetrieverForClaimsProcessing フォルダ内に構築されています。 このコンポーネントは、PolicyValidity データベースからデータを (データセットの形式で) 取得し、ルール条件を評価するために Medical Claims Processing ポリシーによって使用されます。  
  
- 請求の形式は、兄弟要素に保存された名前、ID、請求額、泊数、および日付の情報を含む XML ドキュメントです。  
  
- A。NET ベースのクラス ライブラリ (Claims) は、使用、 **ClaimResults** (ポリシーが有効でない場合) は、潜在顧客を送信して、状態と、プロパティを使用して、要求の理由を記録するクラスが使用を呼び出すことによって、 **SendLeads**ID とパラメーターとして名前を持つメソッド。  
  
  これらのファクト ソースに基づいて、このシナリオについて定義されたルールは、次のように説明できます。  
  
1. 受信した請求が有効かどうかをチェックします。 請求額が限度額を超えている場合、ポリシーの有効期限が切れている場合 (データベース テーブルをチェックすることによって確認)、入院日数が限度を超えている場合、および請求日が将来の日付である場合、請求は無効です。 請求が無効であると判断された場合、請求のステータスおよび理由を適宜設定します。  
  
2. 受信請求のポリシー ID の有効期限が切れている場合は、ポリシー更新部門に情報 (ポリシー ID および患者名) を送信します。  
  
3. 請求が有効な場合は、請求のステータスおよび理由を適宜設定します。  
  
   ルールとその条件のバインドをより形式的に表現すると次のようになります。  
  
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