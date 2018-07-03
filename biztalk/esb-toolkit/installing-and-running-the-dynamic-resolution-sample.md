---
title: インストールして、動的解決サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4359987-b18c-44f5-a2cf-e30e17ac5e9f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0939111bc0a62ecf31286045f412ed160a97c3f9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967731"
---
# <a name="installing-and-running-the-dynamic-resolution-sample"></a>インストールして、動的解決サンプルを実行します。
動的解決サンプルでは、ESB ディスパッチャーと ESB ディスパッチャー逆アセンブラー パイプライン コンポーネントの一般的な使用シナリオを示します。 コンポーネントを使用を動的にエンドポイントの場所を解決するには、ルーティングのプロパティを設定し解決してオーケストレーションを使用しなくても、メッセージング レベルでの Microsoft BizTalk マップを実行する方法を示します。 一方向と双方向の両方のメッセージング パターンも示します。  
  
> [!NOTE]
>  内での解決メカニズムをよく理解しておく場合に最適な結果を得るのため、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]、実行する必要があります、[をインストールして、リゾルバー サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)動的解決サンプルを実行する前にします。  
  
 サンプル アプリケーションを含む 2 つの受信場所と、動的解決のコンポーネントのユース ケースを複数を示すために、サンプルを使用して 2 つの動的送信ポート。 各ユース ケースでは、競合回避モジュールと解像度でアダプター プロバイダーとの組み合わせで使用する場合に、アダプター プロバイダー フレームワークが疎結合のメッセージング ソリューションのさまざまな基礎を提供する方法を示します。  
  
## <a name="one-way-messaging-scenarios"></a>一方向メッセージング シナリオ  
 すべて一方向 (を除く、XPATH の競合回避モジュールを使用する 1 つ) のシナリオの使用を \Source\Samples\DynamicResolution\Test\Data フォルダーにあるファイル NAOrderDoc.xml、メッセージング、受信への入力としてという名前の場所 DynamicResolution_FILE します。 7 つの一方向メッセージングの例は、一意のバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。  
  
## <a name="two-way-messaging-scenarios"></a>双方向メッセージング シナリオ  
 すべての双方向メッセージング シナリオでは、ESB のサンプルを使用します。NorthAmericanServices Web サービスがあるhttp://localhost/ESB.NorthAmericanServices/CustomerOrder.asmx要求メッセージを BizTalk に公開します。 Microsoft InfoPath を使用してこの Web サービスを実行するかから使用可能な Storm などのユーティリティを使って[CodePlex](http://go.microsoft.com/fwlink/?LinkID=187762&clcid=0x409)します。  
  
 それぞれの例は、ESB のサンプル メッセージを送信するエンドポイントの URL を動的に解決します。CanadianServices Web サービスがあるhttp://localhost/ESB.CanadianServices/SubmitPOService.asmxします。 例を実行するか、 **submitOrder**アクションまたは**submitPurchase**解決プロセスの結果に応じて、アクション。 双方向メッセージング シナリオの受信場所では、DynamicResolutionReqResp_SOAP です。 10 の双方向メッセージングの例は、一意のバインドによって表されるすべてのファイルをそれぞれの例を実行する前にインポートする必要があります。  
  
## <a name="binding-files"></a>バインド ファイル  
 このサンプルのバインド ファイルは \Source\Samples\DynamicResolution\Samples\Release という名前のフォルダーにあります。  
  
 すべてのバインド ファイルの名前は、個別に適用する例を示す値を続けて GlobalBank.ESB.DynamicResolution_SubmitOrder_To から始まります。 たとえば、「ファイルの受信ファイルの送信には、静的リゾルバーを使用して」の例のバインド ファイルには、GlobalBank.ESB.DynamicResolution_SubmitOrder_To_FILE_To_FILE_STATIC_Bindings.xml です。  
  
 基になる、GlobalBank.ESB BizTalk アプリケーションにファイルが表示されるバインドのいずれかをインポートするたびにサンプル アプリケーション内の位置がリセットされます。 受信ポート名に関連付けられている動的送信ポート フィルター。 そのため、テストを実行するだけのバインド ファイルのいずれかとドロップするか、適切に名前付きのメッセージを (一方向メッセージング シナリオ) の入力フォルダーにインポートか InfoPath、Storm ユーティリティ、またはその他を使用して NorthAmerican Web サービスを呼び出す適切なクライアント。  
  
## <a name="sample-dependencies"></a>サンプルの依存関係  
 動的解決サンプル数のコア ESB インストールの一部であるアセンブリに依存しています。 これらのアセンブリ、次に示します。  
  
- **Microsoft.Practices.ESB.PipelineComponents.dll**します。 これには、ESB ディスパッチャー パイプライン コンポーネントが含まれています。  
  
- **Microsoft.Practices.ESB.Resolver.dll**します。 これは、パイプラインによって呼び出される Resolver Manager を実装します。  
  
- **Microsoft.Practices.ESB.Resolver.BRE.dll**します。 これは、ビジネス ルール エンジンのリゾルバーを実装します。  
  
- **Microsoft.Practices.ESB.Resolver.STATIC.dll**します。 これは、静的な競合回避モジュールを実装します。  
  
- **Microsoft.Practices.ESB.Resolver.UDDI.dll**します。 これは、UDDI リゾルバーを実装します。  
  
- **Microsoft.Practices.ESB.Resolver.UDDI3.dll**します。 これは、UDDI3 リゾルバーを実装します。  
  
- **Microsoft.Practices.ESB.Resolver.XPATH.dll**します。 これは、XPATH の競合回避モジュールを実装します。  
  
- **Microsoft.Practices.ESB.Resolver.Schemas.dll**します。 これには、競合回避モジュールのスキーマが含まれています。  
  
- **Microsoft.Practices.ESB.Adapter.dll**します。 これは、アダプター マネージャーを実装します。  
  
- **Microsoft.Practices.ESB.Adapter.FTP.dll**します。 これは、FTP アダプターのプロバイダーを実装します。  
  
- **Microsoft.Practices.ESB.Adapter.FILE.dll**します。 これは、ファイル アダプターのプロバイダーを実装します。  
  
- **Microsoft.Practices.ESB.Adapter.MQSeries.dll**します。 これは、MQSeries アダプターのプロバイダーを実装します。  
  
- **Microsoft.Practices.ESB.Adapter.WcfBasicHttp.dll**します。 これは、Wcf-basichttp アダプターのプロバイダーを実装します。  
  
- **Microsoft.Practices.ESB.Adapter.WcfWSHttp.dll**します。 これは、Wcf-wshttp アダプターのプロバイダーを実装します。  
  
  動的解決サンプルも、上記のリゾルバーとアダプターの適切な構成に依存します。 インストールする」の説明に従って、これらの構成のプロセスが完了したことを確認、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
  このセクションのトピックは次のとおりです。  
  
- [動的解決サンプルをインストールする](../esb-toolkit/installing-the-dynamic-resolution-sample.md)  
  
- [動的解決サンプルを実行する](../esb-toolkit/running-the-dynamic-resolution-sample.md)
