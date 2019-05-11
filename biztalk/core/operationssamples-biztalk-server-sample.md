---
title: OperationsSamples (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5101e047c41e12f322639986179b4b87504da75f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262932"
---
# <a name="operationssamples-biztalk-server-sample"></a>OperationsSamples (BizTalk Server サンプル)
OperationsSamples サンプルは、Operations オブジェクト モデルを使用して運用上のアクティビティを実行する方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、次の項目を示しています。  
  
- 追跡プロファイルを使用してアクティビティを使用したオーケストレーションにコメントをする方法。  
  
- BAM 追跡データベースを使用して、アクティビティ ID を検索し、関連するオーケストレーション インスタンスを検索する ID を使用する方法。  
  
- 検索して、メッセージ フローを使用して操作する方法、 **MessageFlow**クラスおよびその他の Operations オブジェクト モデル クラスと Api。  
  
- ポートにアクセスする方法、メッセージ、およびから派生したクラスを使用して他のインスタンス、**インスタンス**クラス。  
  
  このサンプルには、多くの有益なヘルパー クラスと上記の操作をサポートするメソッドが含まれています。 これらおよびその他のコードの特長については、次のセクションで説明します。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルと公開されている BAM 追跡データベースを照会する方法について説明をいくつかの主要なクラスと、Operations オブジェクト モデル内のメソッドを示すために設計されています。  
  
 Operations オブジェクト モデルには、メッセージと BizTalk Server 内では、他のインスタンスを操作する機能を提供するクラスが含まれています。  
  
### <a name="using-a-bam-activity-id"></a>BAM アクティビティ ID を使用します。  
 このサンプルでは、BAM と対話する方法と追跡データベースに公開されているビューを使用して、ビジネス データを使用して、メッセージ ボックスのライブ メッセージを検索する方法を示します。 このサンプルではこの注文書番号に対応するオーケストレーション ID を取得することによって。 このタスクを成功させるには、次に行う必要があります。  
  
1. ビジネス データ (注文書番号) を使用して、アクティビティ ID を検索するには この手順では、ビジネス データを追加情報を見つけるために使用する内部の ID にマップします。  
  
2. アクティビティ ID に関連する BAM 参照を取得します。  
  
3. "BizTalkService"の型であり、オーケストレーションを参照する参照を検索します。 見つかった場合は、そのインスタンス ID を返します  
  
   この機能は、 **BAMWebService.GetOrchestrationID**静的メソッドと、BamManagementService.cs ソース ファイルでクラスとメソッドを含む関連ヘルパー メソッド。  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a>中断、終了、およびインスタンスの再開  
 サンプル プログラムが含まれています、 **Samples.OperateOnInstance**メソッドを操作とインスタンス ID を受け取り、インスタンスで指定された操作を実行します。 有効な操作がによって定義されている、 **InstanceOperation**列挙しており、Suspend、Terminate、再開します。 これらの操作は、biztalkoperations のメソッドに直接マップ-**SuspendInstance**、 **TerminateInstance**、および**ResumeInstance**します。  
  
 メソッドは ArgumentException と SqlException の両方の例外を処理することを確認します。 例外が発生するように注意する必要があります: SqlException を含む、クラスと、Operations オブジェクト モデル内のメソッドを使用する場合。  
  
> [!NOTE]
>  多くの操作メソッドには、データベースへのアクセスが必要です。 これらのメソッドによってスローされた例外を予測し、適切に処理する必要があります。  
  
### <a name="retrieving-all-live-messages"></a>すべてのライブ メッセージを取得します。  
 Operations オブジェクト モデルでは、次のコード フラグメントで示すように、簡単に使用可能なライブ メッセージをすべて繰り返します。  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 OperationsSamples プログラムは、このさらにメッセージ ID とメッセージ部分の数と共にメッセージ型と型を含む、各メッセージに関する情報にアクセスする方法について説明します。 このコードを変更し、BizTalk Server で使用可能なライブ メッセージの一部またはすべてを反復処理するには、あるシナリオで使用できます。  
  
> [!NOTE]
>  ある数百または何千ものメッセージの使用可能です。 リスト全体をスキャンすると、パフォーマンスが低下する可能性があります。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルは、SDK がある次の場所にあります。  
  
 \<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|BamManagementService.cs|BAM Web サービスの web プロキシ クラスです。|  
|Cleanup.bat|サンプル オーケストレーションを削除し、HelloWorld サンプルを元の状態に戻します。|  
|HelloOrchestration.btt|追跡プロファイルが BizTalk イベント ソースを BAM ターゲット アクティビティにマップするために使用します。|  
|HelloOrchestration.xls|BAM 定義スタイル シートです。|  
|OperationsSamples.cs|C# ソース ファイルは、Operations オブジェクト モデルのさまざまな側面を説明するコードを格納しています。|  
|OperationsSamples.csproj、OperationsSamples.sln、AssemblyInfo.cs|このサンプルのプロジェクト、ソリューション、およびアセンブリ情報ファイルです。|  
|Setup.bat|ビルドして HelloWorld オーケストレーション サンプルを変更することでこのサンプルを初期化するために使用します。 これは、コマンドで、サンプル オーケストレーションのインストール、BAM アクティビティ定義と、追跡プロファイル エディター ファイルが展開、ポートの構成、および受信場所にサンプル ファイルをドロップします。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 このサンプルを使用して、Operations オブジェクト モデルで使用可能な機能を試してください。 メッセージを異なる方法で操作を検索して既存のルーチンの変更または BizTalk Server 管理コンソールの グループ ハブの一部を複製する新しいコードを追加します。  
  
 次のタスクのいくつかを検討できます。  
  
-   カスタム アプリケーションに、グループのハブの最も使用頻度のサブセットをレプリケートするアプリケーションを作成します。  
  
-   ポートを作成し、新しい取引を使ってのテスト メッセージを送信するカスタム プロビジョニング アプリケーションを作成します。  
  
-   1 つの発注や、画面、XML ファイル、またはテキスト レポートへの注文書の範囲に関する情報を提供するコマンド ライン ユーティリティには、サンプル プログラムを変更します。  
  
## <a name="installing-sample-support-files"></a>サンプル サポート ファイルをインストールします。  
 このセクションでは、インストールして、サンプルの実行に必要な手順について説明します。  
  
> [!NOTE]
>  インストールして、このサンプルを実行する前に、BAM がインストールされており、機能していることを確認する必要があります。 BAM がインストールされていない場合、このサンプルは機能しません。  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a>コンパイルして、このサンプルのサポート ファイルをインストールするには  
  
1.  コマンド ウィンドウで、次のフォルダーに移動します。  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  次の操作を実行します。 Setup.bat を実行します。  
  
    -   送信を作成し、ディレクトリを受信  
  
    -   作成および送信が開始され、受信ポート  
  
    -   コンパイルし、HelloWorld オーケストレーションの展開、 `<Samples Path>`\Orchestrations\HelloWorld フォルダー。  
  
    -   HelloWorld オーケストレーションの公開キー トークンを変更します。  
  
    -   BAM アクティビティ定義および追跡プロファイル エディター ファイルをデプロイします。  
  
    -   出力ディレクトリの名前を変更します  
  
    > [!NOTE]
    >  インストールを中止するには、最初の"press any key to continue"プロンプトで ctrl キーを押しながら C キーを押します。 これにより、スクリプトを停止し、HelloWorld サンプルの元の状態のままにします。 2 番目と最後のプロンプトで ctrl キーを押しながら C キーを押しても、インストールは停止しません。 この場合、OperationsOM サンプルをアンインストールし、HelloWorld サンプルを復元する Cleanup.bat を実行します。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 次の手順を使用して、OperationsOM サンプルを実行します。  
  
#### <a name="to-compile-and-run-the-sample"></a>コンパイルして、サンプルを実行するには  
  
1.  をクリックして**開始**を選択します**すべてのプログラム**を選択します**Microsoft BizTalk Server**、し、 **BizTalk Server 管理**します。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**ホスト インスタンスの**します。  
  
3.  右クリック**BizTalkServerApplication**、 をクリックし、**再起動**します。  
  
    > [!NOTE]
    >  BizTalkServerApplication ホスト インスタンスを再起動すると、製品を構成してから、ホスト インスタンスを再起動していない場合は、BAM の正しい作業データベースを設定するために必要なことがあります。  
  
4.  Windows エクスプ ローラーで、次のフォルダーに移動します。  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  ダブルクリックして、 **OperationsOM.sln**プロジェクト ファイルを Visual Studio に読み込みます。  
  
6.  F5 キーを押して、サンプルを実行します。  
  
     --または--  
  
     **ビルド** メニューのをクリックして**ソリューションのリビルド**します。 ビルドが完了したらは、Windows エクスプ ローラーを使用して、移動する`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`し、ダブルクリック**OperationsSamples.exe**します。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>クラスまたはメソッドのこのサンプルで使用  
 [Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx) &#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx) &#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx) &#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx) &#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx) &#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)  
  
## <a name="see-also"></a>参照  
 [Admin-OperationsOM (BizTalk Server Samples フォルダー)](../core/admin-operationsom-biztalk-server-samples-folder.md)