---
title: BAM API サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dbc1adba5ef1b0c0a86c456a86ac3cce627d34f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528529"
---
# <a name="bam-api-biztalk-server-sample"></a>BAM API (BizTalk Server サンプル)
BAM API サンプルでは、BAM API の呼び出しを監視できるキーの情報を保存するアプリケーションに組み込む方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、単純な購入シナリオを実装します。 注文書の生成、各注文の処理、出荷、および作成し、請求書を処理します。 サンプルを実行すると、作成し、詳細と注文書や請求書のディス ポジションを反映するように BAM アクティビティを更新します。  
  
## <a name="how-this-sample-was-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 このサンプルは、BAM を使用して、BizTalk オーケストレーションではないアプリケーションの情報を格納する方法を説明するために設計されました。 アプリケーションは、単純なは、実稼働アプリケーションで使用する可能性がある BAM のいくつかの側面を示しています。 その一部を次に示します。  
  
- 1 つのアクティビティに影響を与える複数のスレッド  
  
- 2 つのアクティビティ間のリレーションシップを作成します。  
  
- Continuation を使用して、同じアクティビティに異なる Id を使用してアクセスを許可するには  
  
  BAM API サンプルは、次の 3 つの主要なクラスで構成されます。 1 つは、出荷の処理、請求書を処理する 1 つに、注文購入を処理する 1 つ。 各クラスには、 **RunOnce** 、キューからメッセージを取得し、メッセージを処理するメソッド。 各クラスにはまた、**実行**継続的に呼び出すメソッド、 **RunOnce**メソッド。  
  
  **RunOnce**のメソッド、 **PoApplication**クラスは、次を実行します。  
  
1. 注文書を表す XML メッセージを作成します。  
  
2. BAMApiPo アクティビティを開始し、注文書について、および受信されたときに、アクティビティ情報を追加します。  
  
3. 任意を承認または却下、注文します。  
  
4. 注文書 (承認または拒否) のステータスを記録する BAMApiPo アクティビティを更新します。  
  
5. 注文書が承認された場合、 **RunOnce**メソッドも、次を行います。  
  
   1.  出荷するパッケージを表す XML メッセージを作成し、出荷のキューにメッセージを追加します。  
  
   2.  請求書に含まれる発注書のキューに注文書を表す XML メッセージを追加します。  
  
   3.  BAMApiPo アクティビティの continuation を有効にします。  
  
   4.  BAMApiPo アクティビティを終了します。  
  
   **RunOnce**のメソッド、 **ShipmentApplication**クラスは、次を実行します。  
  
6. 送付先であるパッケージを表す XML メッセージをキューから取得します。  
  
7. パッケージが付属していた時間を記録する BAMApiPo アクティビティを更新します。  
  
8. BAMApiPo アクティビティを終了します。  
  
   **RunOnce**のメソッド、 **InvoiceApplication**クラスは、次を実行します。  
  
9. 請求される注文書を表す XML メッセージをキューから取得します。  
  
10. BAMApiInvoice アクティビティを開始します。  
  
11. BAMApiInvoice アクティビティと BAMApiPo アクティビティを請求される注文書の間の BAM リレーションシップを作成します。  
  
12. 作成された、請求書と、時間に関する BAMApiPo アクティビティ情報を追加します。  
  
13. BAMApiInvoice アクティビティには時間の支払いに請求書の待機をシミュレートするために、請求書の支払いが行われた時刻を追加します。  
  
14. BAMApiInvoice アクティビティを終了します。  
  
    **Main**のメソッド、 **MainApp**クラスが、アプリケーションを初期化します。 その後、次の処理を実行します。  
  
15. 作成、 **DirectEventStream**オブジェクト。  
  
16. いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **POApplication**各スレッドでオブジェクト。  
  
17. いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **ShipmentApplication**各スレッドでオブジェクト。  
  
18. いくつかのスレッドを開始し、呼び出し、**実行**のメソッド、 **InvoiceApplication**各スレッドでオブジェクト。  
  
    **Global**クラスを作成するスレッドの数や拒否する注文書の割合など、サンプル アプリケーションで使用される定数を定義します。  
  
    サンプルには、Visual Studio ソリューションに加え、アクティビティを定義する Microsoft Excel ファイルも含まれます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルで*\<サンプル パス\>* \BAM\BamApiSample します。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|----------|-----------------|  
|BamApiSample.cs|インストルメント化されたアプリケーション。|  
|BamApiSample.csproj|インストルメント化されたアプリケーションのプロジェクトです。|  
|BamApiSample.sln|インストルメント化されたアプリケーションのソリューションです。|  
|BamApiSample.xls|BAM 定義スタイル シートです。|  
|Cleanup.bat|デプロイされたサンプル ファイルを削除するバッチ ファイルです。|  
|Input.txt|サンプルのインターセプタ構成を入力します。|  
|InterceptorConfig.cs|API のサンプルのインターセプタ構成コード。|  
|InterceptorConfig.csproj|インターセプタ構成プロジェクト。|  
|Invoice_config.xml|Invoice インターセプタ構成。|  
|Invoice_interceptor.bin|シリアル化された invoice インターセプタ。|  
|PurchaseOrder_config.xml|PurchaseOrder インターセプタ構成。|  
|PurchaseOrder_interceptor.bin|シリアル化された PurchaseOrder インターセプタ。|  
|Setup.bat|バッチ ファイルを展開し、サンプル ファイルを参加させる。|  
|Shipment_config.xml|Shipment インターセプタ構成。|  
|Shipment_interceptor.bin|シリアル化された shipment インターセプタ。|  
  
## <a name="run-the-bam-api-sample"></a>BAM API サンプルを実行します。  
  
1.  管理者は、コマンド プロンプトを開き、実行*\<サンプル パス\>* \BAM\ BamApiSample\setup.bat します。  
  
2.  管理者は、Visual Studio を起動し、開く、 *\<サンプル パス\>* \BAM\ BamApiSample\BamApiSample.sln ソリューション。 
  
    > [!IMPORTANT]
    >  行`//#define Interceptor`BamApiSample.cs ファイルで、アウト コメントする必要があります。削除しないでください、"//"この行から。 BAM API サンプルは、内部でないコードのみを使用して、`#if Interceptor`プリプロセッサ ディレクティブです。  
  
3.  ソリューションをビルドします。  
  
4.  実行*\<サンプル パス\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe します。  
  
     出力は、次のようになります。  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  しばらくするとそのため、ctrl キーを押しながら C キーを押します。 または BamApiSample プログラムを停止するコマンド プロンプト ウィンドウを閉じます。  
  
## <a name="view-the-results"></a>結果を表示します。
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**、順に展開**テーブル**します。  
  
3.  右クリックして**dbo.bam_BAMApiInvoice_Active**  をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  
  
     Bam_BAMApiInvoice_Active テーブルの内容は、右側のウィンドウに表示されます。 テーブルの各行が開始されたら、完了していない BAMApiInvoice アクティビティを表します。  
  
4.  右クリックして**dbo.bam_BAMApiPo_Completed**  をクリックし、**テーブルを開く**します。 SQL Server を使用している場合はクリックして**上位 1000 行を選択する**します。  
  
     Bam_BAMApiPo_Completed テーブルの内容は、右側のウィンドウに表示されます。 テーブルの各行は、完了した BAMApiPo アクティビティを表します。