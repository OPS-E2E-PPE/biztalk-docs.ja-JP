---
title: 'チュートリアル 1: エコー アダプターの開発 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffb0df3c-cd07-4bcf-af69-971065081fd6
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 484452dc4ee624f4fa41e9387098f6f792c1de28
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="tutorial-1-develop-the-echo-adapter"></a>チュートリアル 1: エコー アダプターを開発します。
このチュートリアルでを開発する機能のアダプターを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 アダプターは、架空の基幹業務システムなど、WCF LOB Adapter SDK の主な機能の多くを説明するための操作をシミュレートします。  
  
-   同期の受信  
  
-   同期送信  
  
-   メタデータの参照  
  
-   メタデータの検索  
  
-   メタデータの解決  
  
 このセクションには、エコー アダプターによってサポートされるさまざまな機能が含まれています。 メッセージ交換、メタデータの操作、接続のプロパティ、およびアダプターのプロパティ。  
  
## <a name="message-exchange-patterns"></a>メッセージ交換パターン  
 エコー アダプターには、次の 2 つのメッセージ交換パターンがサポートされています。  
  
-   同期の送信、つまりがかかり、クライアント、WCF 要求メッセージを送信アダプターを経由して、ターゲット システムに、アダプターを経由して、ターゲット システムから WCF 応答メッセージを受信するまで待機し、します。 これは、アダプターの最も一般的なメッセージ交換パターンです。 送信、同期の実装をサポートするために、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`インターフェイスです。  
  
-   同期の受信、つまり、アダプターを経由して、ターゲット システムからのイベントやデータの使用のクライアント待機です。 受信と、同期の実装をサポートするために、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイスです。  
  
 メッセージ交換のパターンの詳細については、次を参照してください。[アーキテクチャの概要](architecture-overview-of-the-wcf-lob-adapter-sdk.md)です。  
  
> [!NOTE]
>  [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] UI 内のデータ フローとして、メッセージ交換パターンを示しています。  
  
## <a name="metadata-support"></a>メタデータのサポート  
 エコー アダプターは、メタデータの参照、検索、および機能の解決をサポートします。 通常、参照および検索は、LOB システムから、操作を取得します。 エコー アダプターは、LOB システムは、一連の定義済み操作は、次のように。  
  
```  
EchoMainCategory  
        Echo/EchoStrings  
        Echo/EchoGreetings  
        Echo/EchoCustomGreetingFromFile  
        Echo/OnReceiveEcho  
```  
  
 各操作の定義を次に示します。  
  
|**名前**|**操作の定義**|**Description**|**方向**|  
|--------------|------------------------------|---------------------|-------------------|  
|EchoMainCategory|カテゴリ|操作を分類します。|なし|  
|Echo/EchoStrings|string[] EchoStrings(string data)|受信文字列は、呼び出し元のクライアントに指定された回数がエコーされます。|送信|  
|Echo/EchoGreetings|グリーティング:operator[] EchoGreetings(Greeting greeting)|入力方向のあいさつオブジェクト呼び出し元のクライアントに指定された回数がエコーされます。|送信|  
|Echo/EchoCustomGreetingFromFile|CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)|インスタンスをファイルから読み取ることによって、応答メッセージ オブジェクトがエコーされます。 応答メッセージ オブジェクトのメタデータは、定義済みの XSD ファイルから取得されます。|送信|  
|Echo/OnReceiveEcho|OnReceiveEcho (Uri パス、長いコンテンツ) を無効にします。|指定したフォルダーにドロップされたファイルの長さと場所がエコーされます。|受信|  
  
## <a name="adapter-properties"></a>アダプターのプロパティ  
 アダプターは、次のアダプター プロパティを公開します。  
  
|**名前**|**カテゴリ**|**データ型**|**Description**|  
|--------------|------------------|-------------------|---------------------|  
|Count|その他|System.Int32|呼び出し元のクライアントへの入力を指定された回数をエコーするために使用します。<br /><br /> 既定値 5 を =|  
|EnableConnectionPooling|その他|System.Boolean|有効にするか、アダプターの接続のプーリングの無効化するために使用します。<br /><br /> 既定値 = true の場合のランタイム エンジンに接続プールが有効になっていることを意味、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。|  
|InboundFileFilter|受信|System.String|受信のシナリオでのみ使用され、拡張機能のファイルを監視する、FileSystemWatcher で使用します。<br /><br /> 既定値 = * .txt|  
|InboundFileSystemWatcherFolder|受信|System.String|アダプターに通知を発生させる FileSystemWatcher のファイルを削除する場所のフォルダーを設定するために使用します。<br /><br /> 既定の c:\inbound\watcher を = です。|  
  
## <a name="connection-properties"></a>接続プロパティ  
 エコー アダプターは、次の接続プロパティを公開します。  
  
|**名前**|**データ型**|**Description**|  
|--------------|-------------------|---------------------|  
|アプリケーション|System.String|LOB システム内のアプリケーションの名前。 このプロパティは、説明用です。 エコー アダプターは、任意の LOB システムには関与しません。<br /><br /> 既定の lobapplication を =|  
|EnableAuthentication|System.Boolean|True の場合、アダプターはクライアントの資格情報内でユーザー名フィールドの値が必要です。<br /><br /> 既定値 = false|  
|hostname|System.String|LOB システムが存在するサーバーの名前。 このプロパティは、説明用です。 エコー アダプターは、任意の LOB システムには関与しません。<br /><br /> 既定の lobhostname を =|  
  
## <a name="interface-implementation"></a>インターフェイスの実装  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターの特定の機能をサポートするために実装する必要があるクラスとインターフェイスのコレクションを定義します。 次の表は、これらのクラスとインターフェイス、その説明、およびそれらを実装する場合について説明します。  
  
|**クラス/インターフェイス**|**実装する場合**|**Description**|  
|--------------------------|---------------------------|---------------------|  
|Microsoft.ServiceModel.Channels.Common.IConnection|場合は、ターゲット システムへの接続を定義する必要があります。|ターゲット システムへの接続を定義します。|  
|Microsoft.ServiceModel.Channels.Common.IConnectionFactory|場合は、ターゲット システムへの接続を作成する必要があります。|ターゲット システムへの接続を作成します。|  
|Microsoft.ServiceModel.Channels.Common.ConnectionUri|Uri の接続を管理する必要がある場合。<br /><br /> 内の接続プロパティを分類する必要がある場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツールです。|ターゲット システムの接続 Uri を管理します。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler|アダプターでは、メタデータの解決機能をサポートする必要があります。|操作と型のメタデータを解決します。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler|場合は、アダプターは、メタデータの検索機能をサポートします。|ターゲット システム内の操作を検索します。|  
|Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler|アダプターは、[参照] 機能をサポートする必要があります。|ターゲット システム内の操作を参照します。|  
|Microsoft.ServiceModel.Channels.Common.IOutboundHandler|送信機能をサポートするために、アダプターが通常必要がある場合。|受信 WCF 要求メッセージを送信先システムのメッセージに変換、ターゲット システムの特定の関数を呼び出すし、送信 WCF 応答メッセージに応答を変換します。|  
|Microsoft.ServiceModel.Channels.Common.IInboundHandler|場合は、アダプターは、受信機能をサポートします。|データまたはターゲット システムからのイベントをリッスンします。|  
  
 アダプター開発を簡略化を使用して、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]をカスタマイズして、アダプターの機能を派生クラスのセットを作成するアダプター プロジェクトを生成します。  
  
 を通じてアダプターとの接続のプロパティをカスタマイズする、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールによって生成された次のファイルを変更する[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]です。  
  
-   {Projectname}BindingElement.cs  
  
-   {Projectname}BindingElementExtensionElement.cs  
  
-   {Projectname}ConnectionUri.cs  
  
 これを行う方法の詳細については、次を参照してください。[手順 2: アダプターと接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を説明するチュートリアル](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)