---
title: WCF LOB Adapter SDK のアーキテクチャの概要 |Microsoft Docs
description: ハンドラー、チャネルの実装、接続の管理、メタデータ、および WSDL を使用して、WCF LOB Adapter SDK の概要
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbd9b63c-54a4-4f63-b3a8-8600f6009a74
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de1214859a94a05271d2cabc931dcf9531cdcf0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364001"
---
# <a name="architecture-overview-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のアーキテクチャの概要
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は、WCF チャネル モデル上に構築されており、大規模かつダイナミックなメタデータがある基幹業務システムにアダプターを作成するアダプターの開発者向けのデザイン時および実行時の拡張機能を提供します。 アダプターを使用して作成、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]カスタム WCF バインドとしてコンシューマーに表示されます。 次の図は、内部アーキテクチャと WCF LOB Adapter SDK の主要なコンポーネントを示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7183bded-465e-45b9-af78-fbb87cf2df92.gif "7183bded-465e-45b9-af78-fbb87cf2df92")  
  
## <a name="handlers"></a>ハンドラー  
 *ハンドラー*アダプターでサポートされているメッセージ交換パターンを定義します。  
  
 次の表に、使用可能なハンドラー型、それらの機能、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャンネルにマップします。  
  
|**ハンドラーの型**|**関数**|**WCF チャネルに割り当てられます**|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|一方向の送信または要求/応答パターンをサポートしています。|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|非同期の一方向の送信または要求/応答パターンをサポートしています。|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|一方向のサポートは、受信またはパターンを返信します。|IInputChannel,<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|一方向メソッドの非同期のバリエーションをサポートしていますが受信またはパターンを返信します。|IInputChannel<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|サポートは、ターゲット システム上のメタデータの参照。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|ターゲット システム上のメタデータの検索をサポートしています。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|ターゲット システムからのメタデータの取得をサポートしています。|IRequestChannel|  
  
## <a name="channel-implementation"></a>チャネルの実装  
 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は基本的に、トランスポート チャネル (System.ServiceModel.Channels.IServiceListner)。 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]として表示されます、コンシューマーに WCF バインドでは、チャネル スタックを作成するバインドが使用されています。 このバインド BasicHttpBinding、WsHttpBinding、NetTcpBinding などの他の定義済みの WCF バインドのピアと見なすことができます、設定できますコードまたは app.config を使用して、クライアント アプリケーションでサービスを呼び出すとします。 このバインディングには、キー バインド要素 T:System.ServiceModel.Channels.TransportBindingElement クラスから派生したアダプターを使用したバインド要素の順序付けされたセットが含まれています。 送信のシナリオで、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイムはチャネル ファクトリを使用して、アダプター (つまり、トランスポート チャネル) を作成します。 受信のシナリオで、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム サービスのアプリケーションで受信チャネルのチャネル リスナーを利用します。  デザイン時だけでなく、実行時のメッセージは、このコンポーネントを通過します。  
  
## <a name="connection-factory-connection-and-connection-uri-builder"></a>工場出荷時、接続、および接続 URI の接続ビルダー  
 *ConnectionFactory* URI とユーザーの資格情報に基づいて接続を作成するためにファクトリ パターンを提供します。 詳細については、「 `Microsoft.ServiceModel.Channels.Common.IConnectionFactory` 」を参照してください。  
  
 *接続*対象のシステムの低レベルの通信のコントラクトを定義し、ネイティブな通信 Api と接続ハンドルをカプセル化します。 詳細については、「 `Microsoft.ServiceModel.Channels.Common.IConnection` 」を参照してください。  
  
 *接続 Uri ビルダー*により、アダプターのコンシューマー プログラムで構文の特定知識がなくても、接続 Uri を構築します。 詳細については、「 `Microsoft.ServiceModel.Channels.Common.ConnectionUri` 」を参照してください。  
  
## <a name="connection-management"></a>接続の管理  
 *接続の管理*アダプターの接続の有効期間管理を担当します。 内部的に保持、接続プールを使用します。 この接続プールの資格情報は、URI ベースとします。 資格情報にユーザー名が含まれていて、接続のセキュリティ コンテキストを定義するパスワードを実行します。  
  
 同じ資格情報と URI を使用している場合、同じ接続ファクトリで開かれている任意のチャンネルが既にある場合 1 つ使用可能なプールから接続を取得します。  
  
 接続プール マネージャーでは、資格情報に関係なく、チャネル ファクトリの境界を越えて、その URI にするには、開いている接続数のレコードを保持します。 たとえば、1 つのシステムにした別の資格情報を持つ 2 つのユーザー、システムに接続する 2 つのチャネル ファクトリがあることを意味することができます。  
  
> [!NOTE]
>  アダプターでサポートできる接続の数に関する制限があります一般的にシステム リソースによって制限されます。  
  
 アダプター開発者が、接続プール設定を構成に役立つ、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 2 つのクラスを提供します`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`と`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`します。  
  
## <a name="metadata-management"></a>メタデータの管理  
 *メタデータの管理*のターゲット システムのメタデータのキャッシュのオブジェクト指向の表現を担当します。 メタデータに格納できる一般的なキャッシュ アクセス可能なすべての資格情報でも、キャッシュされた資格情報ごとにできます。  
  
 メタデータのライフ サイクルが、デザイン時の定義で始まり実行時に使用状況を継続します。 デザイン時に、アダプター開発者は、操作のセットを特定する必要があり、必要な WSDL とクライアント側のプロキシを生成する必要があります。 アダプター フレームワーク ベースのアダプターは、実行時に定義済みのメタデータを使用して、ターゲット システムの呼び出しから返されるメッセージを解釈します。  
  
 アダプター フレームワークが 3 つのクラスを提供するアダプター ライターのメタデータの設定を構成するには、 `Microsoft.ServiceModel.Channels.Common.CacheSettings`、`Microsoft.ServiceModel.Channels.Common.MetadataSettings`と`Microsoft.ServiceModel.Channels.Common.CommonCacheSettings`します。  
  
## <a name="wsdl-builder"></a>WSDL ビルダー  
 *WSDL ビルダー* (カスタムの WSDL の生成が必要なシナリオがオーバーライドできる)、WCF LOB Adapter SDK の内部メタデータ オブジェクト モデルからの自動の WSDL 生成を提供します。  
  
 参照してください`Microsoft.ServiceModel.Channels.Common.IWsdlRetrieval`詳細についてはします。  
  
## <a name="metadata-browsesearch"></a>メタデータの参照/検索  
 *メタデータの参照/検索*の閲覧と LOB のすべてのメタデータを検索できます。  
  
 詳細については、「 `Microsoft.ServiceModel.Channels.IMetadataRetrievalContract` 」を参照してください。  
  
## <a name="metadata-generation"></a>メタデータの生成  
 *メタデータの生成*(送信シナリオ) 用のクライアント コードを生成するため、アダプターのコンシューマーが選択されている操作に基づいて (受信シナリオ) 用サービス。 場合でも、アダプターのコンシューマーがツールを使用することをお勧め[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] ([!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk アプリケーションが発生した場合)、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]パブリック インターフェイスを提供`Microsoft.ServiceModel.Channels.MetadataRetrievalClient.GetMetadata%2A`を取得しますSystem.Web.Services.Description.ServiceDescription、Web サービス記述言語 (WSDL) 選択した操作と型に関する情報を含むを表します。 アダプターの記述者のメタデータ オブジェクト モデルの使用、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]から派生したクラスを含む`Microsoft.ServiceModel.Channels.Common.OperationMetadata`と`Microsoft.ServiceModel.Channels.Common.TypeMetadata`の各操作の種類の詳細を説明します。  
  