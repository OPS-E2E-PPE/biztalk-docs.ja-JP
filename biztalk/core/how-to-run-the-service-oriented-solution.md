---
title: 指向ソリューションのサービスを実行する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973816"
---
# <a name="how-to-run-the-service-oriented-solution"></a>サービス指向ソリューションの実行方法
次の手順では、単一のコンピュータでサービス指向ソリューションを実行および検証する方法について説明します。 Payment Tracker シミュレーターを開始してから、SOAP トランスポートまたは MQSeries トランスポートを使用して、要求を送信できます (アダプター バージョンおよびインライン バージョンのサービス指向ソリューションには個別の手順を使用します)。  
  
-   [クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。](#step1)  
  
-   [クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。](#step3)  
  
-   [クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。](#step5)  
  
##  <a name="step1"></a>クライアント アプリケーション (スタブ バージョン) を使用して SOAP トランスポートによる要求を送信します。  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a>クライアント アプリケーション (スタブ バージョン) で SOAP トランスポートによる要求を送信するには  
  
1.  コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。  
  
2.  文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。  
  
3.  任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。  
  
4.  選択**SOAP (WS Call)** と**スタブ**で、 **Select Transport and Parameters**グループ ボックス。  
  
5.  次の URL を入力、 **URL**などのテキスト ボックスします。  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
8.  型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
9. をクリックして**my バランス**です。  
  
10. 応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。  
  
     ![スタブ バージョン用のクライアント アプリケーション実行](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")  
  
##  <a name="step3"></a>クライアント アプリケーション (アダプタ バージョン) を使用して要求を送信します。  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a>クライアント アプリケーション (アダプタ バージョン) での要求を送信するには  
  
1.  コマンド プロンプトを開き、ディレクトリに移動\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug と、次のコマンドを起動し実行しますPaymentTracker シミュレーターの場合:  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*キュー マネージャ名* `> 5 [<` *チャネル定義*`>]`  
  
    > [!NOTE]
    >  チャネル定義は、リモート MQSeries Server ではない場合、省略可能です。  
  
    -   Payment Tracker シミュレータを起動したままにします。  
  
2.  コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。  
  
3.  BTSScnSOSimpleClient.exe で、次に示すように、SOAP トランスポートによる要求を送信します。  
  
    1.  文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。  
  
    2.  任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。  
  
    3.  選択**SOAP (WS Call)** と**アダプター**で、 **Select Transport and Parameters**グループ ボックス。  
  
    4.  次の URL を入力、 **URL**などのテキスト ボックスします。  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    6.  型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    7.  をクリックして**my バランス**です。  
  
    8.  応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。  
  
         ![アダプター バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")  
  
4.  BTSScnSOSimpleClient.exe で、MQSeries トランスポートを使用して要求を送信するには、次の操作を行います。  
  
    1.  文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。  
  
    2.  16 桁の数字を入力、**アカウント番号**テキスト ボックス。  
  
    3.  選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。  
  
    4.  型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。 Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>です。  
  
    5.  型`AdapterSOAInputQueue`で、 **Input Queue**テキスト ボックス。  
  
    6.  型`AdapterSOAOutputQueue`で、**出力キュー**テキスト ボックス。  
  
    7.  型\<*チャネル定義*\>で、**チャネル定義**ボックス。 S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>です。  
  
    8.  型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    9. 型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    10. をクリックして**my バランス**です。  
  
    11. 応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。  
  
         ![アダプター バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")  
  
##  <a name="step5"></a>クライアント アプリケーション (インライン バージョン) を使用して要求を送信します。  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a>クライアント アプリケーション (インライン バージョン) での要求を送信するには  
  
1.  コマンド プロンプトを開き、ディレクトリに移動\< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug してから実行して、次のコマンドを開始する、PaymentTracker シミュレーターの場合:  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*キュー マネージャ名* `> 5 [<` *チャネル定義*`>]`  
  
    > [!NOTE]
    >  チャネル定義は、リモート MQSeries Server ではない場合、省略可能です。  
  
    > [!NOTE]
    >  PaymentTracker シミュレーターが既に実行されている場合は、この手順をスキップします。  
  
    -   Payment Tracker シミュレータを起動したままにします。  
  
2.  **BizTalk Server 管理コンソール**、展開 **[btsscn.so.customerservice]** をクリックして**受信場所**を右クリックして **[Paymenttrackingsystemoutputqueue]** をクリックして右側のウィンドウ**を無効にする**です。  
  
    > [!NOTE]
    >  アダプタ バージョンとインライン バージョンでは、同じ MQSeries キュー (LastPaymentsOutputQueue) が使用されます。 2 つのバージョンの競合状態を避けるには、MQSeries キューで受信を待機しているアダプタのバージョンの受信場所を無効にします。  
  
3.  コマンド プロンプトを開き、ディレクトリに移動、 \< *BizTalk Server のインストール ディレクトリ*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release とし、BTSScnSOSimpleClient.exe を実行します。  
  
4.  BTSScnSOSimpleClient.exe で、次に示すように、SOAP トランスポートによる要求を送信します。  
  
    1.  文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。  
  
    2.  任意の 16 桁の数値を入力、**アカウント番号**テキスト ボックス。  
  
    3.  選択**SOAP (WS Call)** と**インライン**で、 **Select Transport and Parameters**グループ ボックス。  
  
    4.  次の URL を入力、 **URL**などのテキスト ボックスします。  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    6.  型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    7.  をクリックして**my バランス**です。  
  
    8.  応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。  
  
         ![インライン バージョンのクライアント アプリケーションを実行](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")  
  
5.  BTSScnSOSimpleClient.exe で、MQSeries トランスポートを使用して要求を送信するには、次の操作を行います。  
  
    1.  文字を入力、 **RequestType**、 **RequestSource**、および**RequestID**テキスト ボックス。  
  
    2.  16 桁の数字を入力、**アカウント番号**テキスト ボックス。  
  
    3.  選択**MQSeries**で、 **Select Transport and Parameters**グループ ボックス。  
  
    4.  型\<*キュー マネージャ名*\>で、**キュー マネージャー**テキスト ボックス。 Qm _\<*コンピューター名を*\>の既定値は、 \<*キュー マネージャ名*\>です。  
  
    5.  型`InlineSOAInputQueue`で、 **Input Queue**テキスト ボックス。  
  
    6.  型`InlineSOAOutputQueue`で、**出力キュー**テキスト ボックス。  
  
    7.  型\<*チャネル定義*\>で、**チャネル定義**ボックス。 S _\<*コンピューター名を*\>/tcp/\<*コンピューター名を*\>(1414) の既定値は、 \< *チャネル定義*\>です。  
  
    8.  型`ZipCode`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    9. 型`CustomerName`で、**名前**下のテキスト ボックス**Authentication Elements**、内の文字を入力し、**値**テキスト ボックス。  
  
    10. をクリックして**my バランス**です。  
  
    11. 応答が表示されます、**応答**テキスト ボックス:**成功**場合に表示されます、要求が正常に処理以外の場合は、要求が失敗した場合、エラー メッセージが表示されます。  
  
         ![インライン バージョンのクライアント アプリケーションを実行](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")  
  
## <a name="see-also"></a>参照  
 [サービス指向ソリューションをインストールする前に](../core/before-installing-the-service-oriented-solution.md)   
 [指向ソリューションのスタブ バージョンのサービスをインストールする方法](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [指向ソリューションのインライン バージョンおよびアダプター バージョンのサービスをインストールする方法](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)