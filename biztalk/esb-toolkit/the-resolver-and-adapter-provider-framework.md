---
title: ESB リゾルバーとアダプターのプロバイダー フレームワーク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb7ea42e-b32c-40a8-b36b-c349f56f6edd
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff6a9b731b981f04f015d8dd644442680c98cbf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399752"
---
# <a name="the-resolver-and-adapter-provider-framework"></a>リゾルバーとアダプターのプロバイダー フレームワーク
リゾルバーとアダプターのプロバイダー フレームワークは、スケジュール、変換、およびエンドポイントの解決とルーティングをサポートします。 フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。 競合回避モジュールの後にコンポーネント (たとえば、送信の Web サービス エンドポイントを検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントの解決、アダプター プロバイダーのコンポーネントが登録済みの BizTalk Server の特定のプロパティを設定アダプター。 たとえば、Wcf-basichttp アダプターのプロバイダーは BizTalk 固有のメッセージ エンドポイントが、特定の BizTalk アダプターを使用する URI のコンテキスト プロパティの設定を行いますFTP アダプターのプロバイダーは、FTP アダプターに固有のプロパティを設定します。  
  
 リゾルバーとアダプターのプロバイダー フレームワークの 1 つの目的は、解決とか、メッセージ レベルで、BizTalk オーケストレーションを使用しなくても、またはオーケストレーション レベルでのルーティングをサポートするためにです。 どちらの場合は、プラグ可能なフレームワークは、簡単な開発、展開、および新しいリゾルバーとアダプター プロバイダーの登録を提供します。 リゾルバーとアダプターのプロバイダーをすべて明確に定義されたインターフェイスを実装して、要求時に読み込まれた構成ファイルでの登録の過程で、実行時に。  
  
 ESB ディスパッチャーおよび ESB ディスパッチャー逆アセンブル パイプライン コンポーネントは、競合回避モジュール マネージャーに SOAP ヘッダーの旅程またはパイプラインの構成のいずれかから接続文字列を渡すことによって、リゾルバーとアダプターのプロバイダー フレームワークを使用します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]構成に登録されているすべてのリゾルバーとアダプター プロバイダーの詳細が含まれています。 実行時、競合回避モジュールのマネージャー、およびアダプター マネージャーの構成ファイルから、登録済みのリゾルバーとアダプター プロバイダーの詳細を読みで、適切なアセンブリを読み込むし、BizTalk ホスト レベルのキャッシュに格納します。 このキャッシュの手法は、繰り返しの構成ファイルの読み取りとすべての送信メッセージに対してアセンブリの読み込みの要件を削除します。  
  
 リゾルバーとアダプターのプロバイダー フレームワークの動作とカスタム競合回避モジュールとアダプターのプロバイダーを作成して拡張する方法を表示する方法の詳細については[を変更して、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。  
  
## <a name="supported-resolution-mechanisms-resolvers"></a>サポートされている解決メカニズム (競合回避モジュール)  
 BizTalk ESB Toolkit には、次の競合回避モジュールが含まれています。**静的、UDDI、UDDI3、XPATH、BRE、BRI、日程表、日程静的**と**LDAP**します。  
  
 競合回避モジュールの接続文字列から成る常に、**モニカー** (など**BRE**) 後に":\\\\"と接続または処理の詳細。 モニカーでは、構成ファイルに関連付けられている競合回避モジュールの定義と一致します。 各接続文字列に関連付けられているプロパティは一意であると、すべてのプロパティが必要です。 競合回避モジュールの各スキーマは、ESB で確認できます。Resolvers.Schemas プロジェクトです。  
  
 接続文字列の例を次に示します。  
  
- **静的**  
  
   STATIC:\\\TransportType=;  
  
   TransportLocation=<http://localhost/ESB.CanadianServices/SubmitPOService.asmx>;  
  
   アクション = です。  
  
   EndPointConfig=;  
  
   JaxRpcResponse = false。  
  
   MessageExchangePattern = です。  
  
   TargetNamespace=<http://globalbank.esb.dynamicresolution.com/canadianservices/>;  
  
   TransformType=;  
  
- **UDDI**  
  
   UDDI:\\\serverUrl=<http://localhost:9901/rmengine>;  
  
   serviceName=OrderPurchaseWebService;  
  
   serviceProvider Microsoft プラクティス ESB を =  
  
- **[XPath]**  
  
   XPATH:\\\TransportType=;  
  
   `TransportLocation=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='ID' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   アクション = です。  
  
   EndPointConfig=;  
  
   JaxRpcResponse = です。  
  
   MessageExchangePattern = です。  
  
   `TargetNamespace=/*[local-name()='OrderDoc' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/']/*[local-name()='customerName' and namespace-uri()='http://globalbank.esb.dynamicresolution.com/northamericanservices/'];`  
  
   TransformType=;  

- **BRE**  
  
   BRE:\\\policy=GetCanadaEndPoint;  
  
   version=;  
  
   useMsg=;  
  
- **BRI**  
  
   BRI:\\\policy=ResolveItinerary;  
  
   version=;  
  
   useMsg=;  
  
- **旅行プラン**  
  
   ITINERARY:\\\name=TwoWayTestItinerary;  
  
   version=;  
  
- **ITINERARY-STATIC**  
  
   ITINERARY-STATIC:\\\name=TwoWayTestItinerary;  
  
   version=;  
  
- **LDAP**  
  
   LDAP:\\\TransportType=SMTP;  
  
   TransportLocation={mail}  
  
   Filter=(&(objectClass=User)(|(userPrincipalName=yourname@domain.com)));  
  
   SearchRoot=;  
  
   SearchScope サブツリー; を =  
  
   EndpointConfig サブジェクトを = = {メール} への旅行プランのテスト メッセージ (& a) 
  
   SMTPAuthenticate = 0 (& a)
  
   SMTPHost=127.0.0.1&
  
   =test@globalbank.com(& A)
  
   DeliveryReceipt = false (& a)
  
   MessagePartsAttachments = 0 (& a)
  
   ReadReceipt = false。  
  
   ThrowErrorIfNotFound = false。  
  
   アクション = です。  
  
   JaxRpcResponse = false。  
  
   MessageExchangePattern = です。  
  
   TargetNamespace = です。  
  
   TransformType=;  
  
  接続文字列内のすべての属性は必須です。 さらに、 **EndPointConfig**は特別な属性の競合回避モジュールは設定し、返します。 必要に応じて、競合回避モジュールは、BizTalk メッセージのコンテキストは書き込み可能にすると、さらに、特定の BizTalk アダプター コンテキスト プロパティに対応する名前/値ペアを格納できます。  
  
  ここで、 **ResolverDictionary**アダプター マネージャーにし、解決プロセス、パスから解決されたすべてのプロパティを含むインスタンスが返されます。 ディクショナリは、アダプター マネージャーは、すべてのアダプター固有およびエンドポイント固有 BizTalk コンテキストにメッセージのプロパティを設定する特定のアダプター プロバイダーに渡します。 競合回避モジュールを探して、 **EndPointConfig**プロパティは、それぞれのアダプターのプロパティに対応する名前/値ペアを抽出し、メッセージにこれらの値を設定します。  
  
## <a name="supported-adapter-providers"></a>サポートされているアダプターのプロバイダー  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の組み込みのアダプターのプロバイダーが含まれています。**ファイル、FTP、SMTP、MQSeries、Wcf-basichttp、Wcf-wshttp、** と**Wcf-custom**します。 各アダプター プロバイダーの名前は、BizTalk Server では、関連付けられているアダプター (トランスポートの種類) の名前と同じです。  
  
 リゾルバーとアダプターのプロバイダー フレームワークの主な利点を作成し、エンドポイント情報とカスタム アダプター プロバイダーが登録済みの BizTalk アダプターの特定のプロパティの設定を解決するのには独自のカスタム リゾルバーを登録して拡張できます。 詳細については、次を参照してください。[を変更すると、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。
