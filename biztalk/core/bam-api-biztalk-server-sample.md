---
title: "BAM API (BizTalk Server サンプル) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, APIs
- examples, BAM
- BAM, examples
- APIs, BAM
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f65b98871f054d96caa278e48de19ad669157b1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="bam-api-biztalk-server-sample"></a>BAM API (BizTalk Server サンプル)
BAM API サンプルでは、BAM API の呼び出しを監視することが重要な情報を保存するアプリケーションに組み込む方法を示します。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルは、単純な購入のシナリオを実装します。 注文書の生成、各注文書の処理、出荷、および請求書の作成と処理を行います。 このサンプルを実行すると、BAM アクティビティが作成および更新され、注文書と請求書の詳細と処理が反映されます。  
  
## <a name="how-this-sample-was-designed-and-why"></a>このサンプルをデザインした方法とその理由  
 このサンプルは、BAM を使用して、BizTalk オーケストレーションではないアプリケーションの情報を保存する方法を示すためにデザインされました。 アプリケーションは単純ですが、実稼働環境のアプリケーションでも使用できる BAM のいくつかの側面が示されています。 その一部を次に示します。  
  
-   単一のアクティビティを構成する複数のスレッド  
  
-   2 つのアクティビティの間でリレーションシップの作成  
  
-   別の ID を使用して同じアクティビティにアクセスできるようにする Continuation の使用  
  
 BAM API サンプルは、3 つのメイン クラスで構成されます。注文書を処理するためのクラス、出荷を処理するためのクラス、および請求書を処理するためのクラスです。 各クラスには、 **RunOnce**キューからメッセージを取得し、メッセージを処理するメソッド。 各クラスにはまた、**実行**継続的に呼び出すメソッド、 **RunOnce**メソッドです。  
  
 **RunOnce**のメソッド、 **PoApplication**クラスは、次を実行します。  
  
1.  注文書を表す XML メッセージを作成します。  
  
2.  BAMApiPo アクティビティを開始し、注文書および注文書の受信時刻に関する情報をアクティビティに追加します。  
  
3.  適宜、注文書を承認または拒否します。  
  
4.  BAMApiPo アクティビティを更新して注文書の状況 (承認または拒否) を記録します。  
  
5.  注文が受け入れられた場合、 **RunOnce**メソッドは次も実行します。  
  
    1.  出荷されるパッケージを表す XML メッセージを作成し、出荷のキューにメッセージを追加します。  
  
    2.  注文書を表す XML メッセージを、請求書に含める注文書のキューに追加します。  
  
    3.  BAMApiPo アクティビティの Continuation を有効にします。  
  
    4.  BAMApiPo アクティビティを終了します。  
  
 **RunOnce**のメソッド、 **ShipmentApplication**クラスは、次を実行します。  
  
1.  出荷されるパッケージを表す XML メッセージをキューから取得します。  
  
2.  BAMApiPo アクティビティを更新してパッケージが出荷された時刻を記録します。  
  
3.  BAMApiPo アクティビティを終了します。  
  
 **RunOnce**のメソッド、 **InvoiceApplication**クラスは、次を実行します。  
  
1.  請求される注文書を表す XML メッセージをキューから取得します。  
  
2.  BAMApiInvoice アクティビティを開始します。  
  
3.  請求される注文書の BAMApiInvoice アクティビティと BAMApiPo アクティビティの間に BAM リレーションシップを作成します。  
  
4.  請求書と請求書の作成時刻に関する情報を BAMApiPo アクティビティに追加します。  
  
5.  請求書が支払われるまでの待機時間をシミュレートするためにしばらく間を置いて、BAMApiInvoice アクティビティに請求書の支払いが行われた時刻を追加します。  
  
6.  BAMApiInvoice アクティビティを終了します。  
  
 **Main**のメソッド、 **MainApp**クラスは、アプリケーションを初期化します。 その後、次の処理を実行します。  
  
1.  作成、 **DirectEventStream**オブジェクト。  
  
2.  複数のスレッドを開始を呼び出すと、**実行**のメソッド、 **POApplication**各スレッドでのオブジェクト。  
  
3.  複数のスレッドを開始を呼び出すと、**実行**のメソッド、 **ShipmentApplication**各スレッドでのオブジェクト。  
  
4.  複数のスレッドを開始を呼び出すと、**実行**のメソッド、 **InvoiceApplication**各スレッドでのオブジェクト。  
  
 **グローバル**クラスを作成するスレッドの数や拒否する注文書の割合など、サンプル アプリケーションで使用される定数を定義します。  
  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ソリューションに加えて、このサンプルにはアクティビティを定義する Microsoft [!INCLUDE[btsExcel](../includes/btsexcel-md.md)] ファイルも含まれています。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 このサンプルを見つけることができます*\<サンプル パス\>*\BAM\BamApiSample です。  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|Description|  
|----------|-----------------|  
|BamApiSample.cs|インストルメント化されたアプリケーション。|  
|BamApiSample.csproj|インストルメント化されたアプリケーション プロジェクト。|  
|BamApiSample.sln|インストルメント化されたアプリケーション ソリューション。|  
|BamApiSample.xls|BAM 定義スタイルシート。|  
|Cleanup.bat|展開されたサンプル ファイルを削除するバッチ ファイル。|  
|Input.txt|インターセプタ構成入力のサンプル。|  
|InterceptorConfig.cs|API サンプルのインターセプタ構成コード。|  
|InterceptorConfig.csproj|インターセプタ構成プロジェクト。|  
|Invoice_config.xml|Invoice インターセプタ構成。|  
|Invoice_interceptor.bin|シリアル化された Invoice インターセプタ。|  
|PurchaseOrder_config.xml|PurchaseOrder インターセプタ構成。|  
|PurchaseOrder_interceptor.bin|シリアル化された PurchaseOrder インターセプタ。|  
|Setup.bat|サンプル ファイルを展開して参加するバッチ ファイル。|  
|Shipment_config.xml|Shipment インターセプタ構成。|  
|Shipment_interceptor.bin|シリアル化された Shipment インターセプター。|  
  
## <a name="how-to-use-this-sample"></a>このサンプルの使用方法  
 BAM API サンプルを実行して結果を表示するには、次の手順を実行します。  
  
#### <a name="to-run-the-bam-api-sample"></a>BAM API サンプルを実行するには  
  
1.  コマンド プロンプトを開き、実行*\<サンプル パス\>*\BAM\ BamApiSample\setup.bat です。 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者としてコマンド プロンプトを開きます。  
  
2.  開始[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]を開き、 *\<サンプル パス\>*\BAM\ BamApiSample\BamApiSample.sln ソリューションです。 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、管理者として [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を起動します。  
  
    > [!IMPORTANT]
    >  BamApiSample.cs ファイルの `//#define Interceptor` の行をコメント化します。この行から "//" を削除しないでください。 BAM API サンプルでは、`#if Interceptor` プリプロセッサ ディレクティブ内にないコードのみを使用します。  
  
3.  ソリューションをビルドします。  
  
4.  実行*\<パスのサンプル\>*\BAM\BamApiSample\bin\debug\BamApiSample.exe です。  
  
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
  
5.  1 分ほど経ったら、Ctrl キーを押しながら C キーを押すか、コマンド プロンプト ウィンドウを閉じて、BamApiSample プログラムを停止します。  
  
#### <a name="to-view-the-results-of-running-the-bam-api-sample"></a>BAM API サンプルの実行結果を表示するには  
  
1.  SQL Server Management Studio を開きます。  
  
2.  SQL Server Management Studio で、サーバーを展開し、**データベース**、展開**BAMPrimaryImport**の順に展開および**テーブル**です。  
  
3.  右クリック**dbo.bam_BAMApiInvoice_Active**  をクリックし、**テーブルを開く**です。 SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。  
  
     bam_BAMApiInvoice_Active テーブルの内容が右側のウィンドウに表示されます。 テーブルの各行は、開始されているが、完了していない BAMApiInvoice アクティビティを表します。  
  
4.  右クリック**dbo.bam_BAMApiPo_Completed**  をクリックし、**テーブルを開く**です。 SQL Server を使用している場合はクリックして**上位 1000 行を選択して**です。  
  
     bam_BAMApiPo_Completed テーブルの内容が右側のウィンドウに表示されます。 テーブルの各行は、完了した BAMApiPo アクティビティを表します。