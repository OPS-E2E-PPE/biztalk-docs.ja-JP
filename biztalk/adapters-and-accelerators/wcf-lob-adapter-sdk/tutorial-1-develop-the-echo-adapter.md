---
title: チュートリアル 1:エコー アダプターの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffb0df3c-cd07-4bcf-af69-971065081fd6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff9d3aa911785640cc0ea5f4d6e4deedc10d81c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363069"
---
# <a name="tutorial-1-develop-the-echo-adapter"></a>チュートリアル 1:エコー アダプターを開発します。
このチュートリアルでアダプターの機能を使用して、開発は、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 アダプターは、WCF LOB Adapter SDK などの主な機能の多くを架空の基幹業務システムの操作をシミュレートします。  

- 同期受信  

- 同期送信  

- メタデータの参照  

- メタデータの検索  

- メタデータの解決  

  このセクションには、エコー アダプターでサポートされているさまざまな機能が含まれています。 メッセージ交換、メタデータの操作、接続のプロパティ、およびアダプターのプロパティは。  

## <a name="message-exchange-patterns"></a>メッセージ交換パターン  
 エコー アダプターには、次の 2 つのメッセージ交換パターンがサポートされています。  

- 送信、つまり、消費クライアントはターゲット システムにアダプターを経由して、WCF 要求メッセージを送信およびアダプターを経由して、ターゲット システムから WCF 応答メッセージを受信するまで待機し、同期します。 これは、アダプターの最も一般的なメッセージ交換パターンです。 送信同期の実装をサポートするために、`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`インターフェイス。  

- 同期受信は、データまたはアダプターを経由して、ターゲット システムからのイベントがかかるクライアントが受信を待機します。 受信すると、同期の実装をサポートするために、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`インターフェイス。  

  メッセージ交換パターンの詳細については、次を参照してください。[アーキテクチャの概要](architecture-overview-of-the-wcf-lob-adapter-sdk.md)します。  

> [!NOTE]
>  [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] UI 内のデータ フローとして、メッセージ交換パターンを示しています。  

## <a name="metadata-support"></a>メタデータのサポート  
 エコー アダプター メタデータの参照、検索、および機能の解決をサポートしています。 通常、参照および検索は、LOB システムから操作を取得します。 エコー アダプターの場合は、LOB システムは、次に示すように一連の定義済みの操作は。  

```  
EchoMainCategory  
        Echo/EchoStrings  
        Echo/EchoGreetings  
        Echo/EchoCustomGreetingFromFile  
        Echo/OnReceiveEcho  
```  

 各操作の定義を次に示します。  

|**名前**|**操作の定義**|**[説明]**|**[方向]**|  
|--------------|------------------------------|---------------------|-------------------|  
|EchoMainCategory|カテゴリ|操作を分類します。|なし|  
|Echo/EchoStrings|string[] EchoStrings(string data)|受信文字列は、呼び出し元のクライアントに指定された回数をエコーします。|送信|  
|エコー/EchoGreetings|EchoGreetings(Greeting greeting) のあいさつ|受信応答メッセージ オブジェクト、呼び出し元のクライアントに指定された回数をエコーします。|送信|  
|Echo/EchoCustomGreetingFromFile|CustomGreeting EchoCustomGreetingFromFile(Uri greetingInstancePath)|ファイルからそのインスタンスを参照して、応答メッセージ オブジェクトをエコーします。 応答メッセージ オブジェクトのメタデータは、定義済みの XSD ファイルから取得されます。|送信|  
|エコー/OnReceiveEcho|OnReceiveEcho (Uri パス、時間の長いコンテンツ) を無効にします。|指定したフォルダーにドロップしたファイルの長さと場所をエコーします。|受信|  

## <a name="adapter-properties"></a>アダプターのプロパティ  
 アダプターは、次のアダプター プロパティを公開します。  


|            **名前**            | **カテゴリ** | **[データ型]**  |                                                                                                              **[説明]**                                                                                                               |
|--------------------------------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|             Count              |     その他     |  System.Int32  |                                                                    呼び出し元のクライアントへの入力を指定した回数をエコーするために使用します。<br /><br /> 既定 = 5                                                                     |
|    EnableConnectionPooling     |     その他     | System.Boolean | 有効にするか、アダプターの接続のプールを無効にするために使用します。<br /><br /> 既定値 = true の場合、ランタイム エンジンの接続プールが有効になっていることを意味、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 |
|       InboundFileFilter        |   受信    | System.String  |                                                   受信のシナリオでのみ使用され、filesystemwatcher クラスの拡張機能のファイルを監視するために使用します。<br /><br /> 既定 =\*.txt                                                   |
| InboundFileSystemWatcherFolder |   受信    | System.String  |                                        アダプターに通知を発生させる FileSystemWatcher のファイルを削除、フォルダーを設定するために使用します。<br /><br /> 既定の c:\inbound\watcher を = です。                                        |

## <a name="connection-properties"></a>接続プロパティ  
 エコー アダプターは、次の接続プロパティを公開します。  

|**名前**|**[データ型]**|**[説明]**|  
|--------------|-------------------|---------------------|  
|アプリケーション|System.String|LOB システム内でアプリケーションの名前。 このプロパティは、説明用です。 エコー アダプターは、任意の LOB システムには関与しません。<br /><br /> 既定の lobapplication を =|  
|EnableAuthentication|System.Boolean|True の場合、アダプターは、クライアント資格情報内のユーザー名フィールドの値が必要です。<br /><br /> 既定値 = false|  
|hostname|System.String|LOB システムが存在するサーバーの名前。 このプロパティは、説明用です。 エコー アダプターは、任意の LOB システムには関与しません。<br /><br /> 既定の lobhostname を =|  

## <a name="interface-implementation"></a>インターフェイスの実装  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターの特定の機能をサポートするために実装する必要があるクラスとインターフェイスのコレクションを定義します。 次の表では、これらのクラスとインターフェイス、その説明、およびそれらを実装する場合について説明します。  


|                       **クラス/インターフェイス**                       |                                                                                       **いつ実装するには**                                                                                        |                                                                                      **[説明]**                                                                                       |
|-----------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|       Microsoft.ServiceModel.Channels.Common.IConnection        |                                                                     場合は、ターゲット システムへの接続を定義する必要があります。                                                                     |                                                                        ターゲット システムへの接続を定義します。                                                                        |
|    Microsoft.ServiceModel.Channels.Common.IConnectionFactory    |                                                                      場合は、ターゲット システムへの接続を作成する必要があります。                                                                      |                                                                        ターゲット システムへの接続を作成します。                                                                        |
|      Microsoft.ServiceModel.Channels.Common.ConnectionUri       | 接続 Uri を管理する必要があります。 場合、<br /><br /> 内の接続プロパティを分類する必要がある場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]ツール。 |                                                                      ターゲット システムの接続 Uri を管理します。                                                                       |
| Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler |                                                                       アダプターでは、メタデータの解決機能をサポートする必要があります。                                                                       |                                                                           操作と型のメタデータを解決します。                                                                            |
|  Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler  |                                                                        場合は、アダプター メタデータの検索機能をサポートしています。                                                                        |                                                                   ターゲット システム内の操作を検索します。                                                                    |
|  Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler  |                                                                            アダプターは、参照機能をサポートする必要があります。                                                                             |                                                                    ターゲット システム内で操作を参照します。                                                                    |
|     Microsoft.ServiceModel.Channels.Common.IOutboundHandler     |                                                                  送信機能をサポートするために、アダプターが通常必要がある場合。                                                                   | 対象のシステム メッセージに、着信 WCF 要求メッセージを変換、ターゲット システムの特定の関数を呼び出す送信 WCF 応答メッセージに応答を変換します。 |
|     Microsoft.ServiceModel.Channels.Common.IInboundHandler      |                                                                            場合は、アダプターは、受信機能をサポートします。                                                                            |                                                                   データや、ターゲット システムからのイベントをリッスンします。                                                                   |

 使用して、アダプターの開発を簡素化する、[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]一連のアダプターの機能に合わせて調整する派生クラスを作成し、アダプター プロジェクトを生成します。  

 アダプターと接続プロパティをカスタマイズする、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]ツールによって生成された次のファイルを変更する[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]します。  

- {Projectname}BindingElement.cs  

- {Projectname}BindingElementExtensionElement.cs  

- {Projectname}ConnectionUri.cs  

  これを行う方法の詳細については、次を参照してください。[手順 2。アダプターおよび接続のプロパティを分類](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-2-categorize-the-adapter-and-connection-properties.md)します。  

## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK についてのチュートリアル](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)