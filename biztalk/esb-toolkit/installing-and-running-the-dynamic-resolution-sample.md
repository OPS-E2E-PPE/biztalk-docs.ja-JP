---
title: "インストールして、動的な解決サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f93396fc71c9e765104ac67835e006e57ca0ade
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>インストールして、動的な解決サンプルを実行します。
動的解決サンプルでは、ESB ディスパッチャーと ESB ディスパッチャーの逆アセンブラー パイプライン コンポーネントの一般的な使用シナリオを示します。 これは、動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し、解決するにはおよびオーケストレーションを使用しなくても、メッセージ レベルでの Microsoft BizTalk マップを実行するコンポーネントを使用する方法について説明します。 また、一方向と双方向の両方のメッセージング パターンを示します。  
  
> [!NOTE]
>  内での解決メカニズムをよく理解しておく場合に最適な結果を[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、実行する必要があります、[をインストールして、リゾルバー サービスのサンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)動的解決のサンプルを実行する前にします。  
  
 サンプル アプリケーションを含む 2 つの受信場所と動的解決のコンポーネントのユース ケースのサンプルを複数を示すために使用する 2 つの動的送信ポート。 各ユース ケースでは、競合回避モジュールとは、解像度でアダプター プロバイダーの組み合わせで使用するときに、アダプター プロバイダー フレームワークが、さまざまな疎結合のメッセージング ソリューションの基礎を提供する方法を示します。  
  
## <a name="one-way-messaging-scenarios"></a>一方向のメッセージング シナリオ  
 \Source\Samples\DynamicResolution\Test\Data フォルダーにあるファイル NAOrderDoc.xml、(を除く、XPATH の競合回避モジュールを使用して) シナリオの使用をメッセージングすべて一方向受信への入力としての場所の名前 DynamicResolution_FILE です。 7 つの一方向メッセージングの例は、一意なバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。  
  
## <a name="two-way-messaging-scenarios"></a>双方向のメッセージング シナリオ  
 双方向のすべてのメッセージング シナリオでは、ESB のサンプルを使用します。BizTalk に要求メッセージを発行する http://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx にある NorthAmericanServices Web サービスです。 Microsoft InfoPath を使用してこの Web サービスを実行できるかなどから利用可能な Storm ユーティリティを使って[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)です。  
  
 それぞれの例は、動的にサンプル ESB にメッセージを送信するエンドポイントの URL を解決します。http://localhost/ESB.CanadianServices/SubmitPOService.asmx にある CanadianServices Web サービスです。 例を実行するか、 **submitOrder**アクションまたは**submitPurchase**解決プロセスの結果に応じて、アクション。 双方向のメッセージング シナリオの受信場所は、DynamicResolutionReqResp_SOAP です。 10 の双方向メッセージングの例は、一意なバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。  
  
## <a name="binding-files"></a>バインド ファイル  
 このサンプルのバインド ファイルは \Source\Samples\DynamicResolution\Samples\Release をという名前のフォルダーにあります。  
  
 すべてのバインド ファイルの名前は、個別に適用する例を示す値を続けて GlobalBank.ESB.DynamicResolution_SubmitOrder_To から始めてください。 たとえば、「ファイルの送信がファイル受信では、静的なリゾルバーを使用して」例については、バインド ファイルは GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml です。  
  
 ファイルを基になる GlobalBank.ESB BizTalk アプリケーションには、バインディングのいずれかをインポートするたびに、サンプル アプリケーション内の位置がリセットされます。 受信ポート名に関連付けられている動的送信ポート フィルター。 そのため、テストを実行するだけのバインド ファイルのいずれかと、ドロップ適切に名前付きのメッセージを (一方向のメッセージング シナリオ) の入力フォルダにインポートまたはする InfoPath、Storm ユーティリティ、またはその他を使用して、NorthAmerican Web サービスを呼び出す適切なクライアント。  
  
## <a name="sample-dependencies"></a>サンプルの依存関係  
 動的解決のサンプルは、コア ESB インストールの一部であるアセンブリの数に依存しています。 これらのアセンブリは次のとおりです。  
  
-   **Microsoft.Practices.ESB.PipelineComponents.dll**です。 これには、ESB ディスパッチャー パイプライン コンポーネントが含まれています。  
  
-   **Microsoft.Practices.ESB.Resolver.dll**です。 これは、パイプラインによって呼び出されますリゾルバー マネージャーを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.BRE.dll**です。 これは、ビジネス ルール エンジン競合回避モジュールを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.STATIC.dll**です。 これは、静的な競合回避モジュールを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI.dll**です。 これは、UDDI リゾルバーを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.UDDI3.dll**です。 これは、UDDI3 リゾルバーを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.XPATH.dll**です。 これは、XPATH の競合回避モジュールを実装します。  
  
-   **Microsoft.Practices.ESB.Resolver.Schemas.dll**です。 これには、競合回避モジュールのスキーマが含まれています。  
  
-   **Microsoft.Practices.ESB.Adapter.dll**です。 これには、アダプター マネージャーを実装します。  
  
-   **Microsoft.Practices.ESB.Adapter.FTP.dll**です。 これは、FTP アダプターのプロバイダーを実装します。  
  
-   **Microsoft.Practices.ESB.Adapter.FILE.dll**です。 これは、ファイル アダプターのプロバイダーを実装します。  
  
-   **Microsoft.Practices.ESB.Adapter.MQSeries.dll**です。 これは、MQSeries アダプターのプロバイダーを実装します。  
  
-   **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**です。 これは、Wcf-basichttp アダプター プロバイダーを実装します。  
  
-   **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**です。 これは、Wcf-wshttp アダプター プロバイダーを実装します。  
  
 動的解決のサンプルは、前の競合回避モジュールとアダプターの適切な構成に依存するもできます。 インストールする」の説明に従って、これらの構成のプロセスが完了することを確認してください、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 このセクションのトピックは次のとおりです。  
  
-   [動的解決サンプルをインストールする](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
-   [動的解決サンプルを実行する](../esb-toolkit/running-the-dynamic-resolution-sample.md)
