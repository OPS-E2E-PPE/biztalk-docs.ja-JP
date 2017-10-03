---
title: "WCF LOB Adapter SDK のアーキテクチャの概要 |Microsoft ドキュメント"
description: "ハンドラー、チャネルの実装、接続の管理、メタデータ、および WCF LOB Adapter SDK での WSDL の使用の概要"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dbd9b63c-54a4-4f63-b3a8-8600f6009a74
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86d2104fff0e227d9cdda4c9fb3faf1ea7cb84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のアーキテクチャの概要
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]は、WCF チャネル モデル上に構築され、大きなおよび動的なメタデータがある基幹業務システムにアダプターを作成するアダプターの開発者向けのデザイン時および実行時の拡張機能を提供します。 使用して作成されたアダプタ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]はカスタム WCF バインドとしてコンシューマーを確認します。 次の図は、内部のアーキテクチャと WCF LOB Adapter SDK の主要なコンポーネントを示します。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7183bded-465e-45b9-af78-fbb87cf2df92.gif "7183bded-465e-45b9-af78-fbb87cf2df92")  
  
## <a name="handlers"></a>ハンドラー  
 *ハンドラー*アダプターでサポートされているメッセージ交換パターンを定義します。  
  
 次の表に、使用できるハンドラーの型、それらの機能、および[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネルにマップします。  
  
|**ハンドラーの種類**|**関数**|**WCF チャネルへのマップ**|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|一方向の送信、または要求/応答パターンをサポートしています。|IOutputChannel、<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|非同期の一方向の送信、または要求/応答パターンをサポートしています。|IOutputChannel、<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|一方向のサポートは、受信またはパターンを返信します。|IInputChannel、<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|一方向のメソッドの非同期のバリエーションをサポートでは、受信またはパターンを返信します。|IInputChannel<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|サポートは、ターゲット システム上のメタデータの参照。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|ターゲット システム上のメタデータの検索をサポートしています。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|対象システムからのメタデータの取得をサポートしています。|IRequestChannel|  
  
## <a name="channel-implementation"></a>チャネルの実装  
 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]トランスポート チャネル (System.ServiceModel.Channels.IServiceListner) は、基本的にします。 使用して構築されたアダプター、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提示されるコンシューマーに、WCF バインドとチャネル スタックを作成するバインディングが使用されています。 このバインディングは、BasicHttpBinding、WsHttpBinding、NetTcpBinding などの他の定義済みの WCF バインディングのピアと見なされます。 として設定できますまたはコードを app.config を使用して、クライアント アプリケーション サービスを呼び出すときにします。 このバインディングには、T:System.ServiceModel.Channels.TransportBindingElement クラスから派生するキーのバインド要素をされているアダプターとバインド要素の順序付きセットが含まれています。 送信のシナリオで、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイムでは、チャネル ファクトリを使用して、アダプター (トランスポート チャネルは、) を作成します。 受信のシナリオで、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイムでは、チャネル リスナーをサービス アプリケーションで受信チャネルを使用します。  デザイン時だけでなく、実行時のメッセージは、このコンポーネントを通過します。  
  
## <a name="connection-factory-connection-and-connection-uri-builder"></a>接続ファクトリ、接続、および接続 URI のビルダー  
 *ConnectionFactory* URI とユーザーの資格情報に基づいて接続を作成するためにファクトリ パターンを提供します。 詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`です。  
  
 *接続*ターゲット システムでの低レベルの通信のコントラクトを定義し、ネイティブな通信の Api と接続ハンドルをカプセル化します。 詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.IConnection`です。  
  
 *接続 Uri ビルダー*アダプター コンシューマー プログラムで構文の特定の知識なしの接続 Uri を構築する関数を使用します。 詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.Common.ConnectionUri`です。  
  
## <a name="connection-management"></a>接続の管理  
 *接続の管理*アダプターの接続の有効期間管理を担当します。 内部的に保たれます、接続プールを使用可能。 この接続プールの資格情報は、URI ベースとします。 資格情報には、ユーザー名が含まれています。 し、セキュリティ コンテキストの接続を定義するパスワードを実行します。  
  
 同じ資格情報と URI を使用している場合、同じ接続ファクトリで開いているすべてのチャネルが既にある場合 1 つ使用可能なプールから接続を取得します。  
  
 接続プール マネージャーでは、資格情報に関係なく、チャネル ファクトリの境界を越えて、その URI には、開いている接続の数のレコードが保持されます。 たとえば、1 つのシステムした別の資格情報を持つ 2 つのユーザー システムに接続する 2 つのチャネル ファクトリがあることを意味することができます。  
  
> [!NOTE]
>  アダプターがこれをサポートできますが、接続の数に関する限られた可能性があります、通常のシステム リソースによって制限されます。  
  
 アダプター開発者が接続プール設定を構成するのに役立つ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の 2 つのクラスを提供`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`と`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`です。  
  
## <a name="metadata-management"></a>メタデータの管理  
 *メタデータの管理*は、オブジェクト指向の形式は、ターゲット システムのメタデータのキャッシュを担当します。 メタデータ保持できる共通のキャッシュにアクセスできるすべての資格情報でも、キャッシュされた資格情報ごとにできます。  
  
 メタデータのライフ サイクルは、デザイン時の定義とが開始され、実行時に、使用方法によっては続行されます。 デザイン時に、アダプター開発者は、操作のセットを識別する必要があり、必要な WSDL とクライアント側プロキシを生成する必要があります。 実行時に、アダプター フレームワークに基づいたアダプターでは、定義済みのメタデータを使用し、ターゲット システムの呼び出しから返されるメッセージを解釈できます。  
  
 アダプター フレームワークはアダプター ライターのメタデータの設定を構成するために、3 つのクラスを提供`Microsoft.ServiceModel.Channels.Common.CacheSettings`、`Microsoft.ServiceModel.Channels.Common.MetadataSettings`と`Microsoft.ServiceModel.Channels.Common.CommonCacheSettings`です。  
  
## <a name="wsdl-builder"></a>WSDL ビルダー  
 *WSDL ビルダー* (カスタムの WSDL の生成を必要とするシナリオの上書きできます)、WCF LOB Adapter SDK の内部メタデータ オブジェクト モデルから自動 WSDL の生成を提供します。  
  
 参照してください`Microsoft.ServiceModel.Channels.Common.IWsdlRetrieval`詳細についてはします。  
  
## <a name="metadata-browsesearch"></a>メタデータの参照/検索  
 *メタデータの参照/検索*では、参照および LOB のすべてのメタデータを検索します。  
  
 詳細については、次を参照してください。`Microsoft.ServiceModel.Channels.IMetadataRetrievalContract`です。  
  
## <a name="metadata-generation"></a>メタデータの生成  
 *メタデータの生成*により、(送信シナリオ) 用のクライアントのコードを生成するため、操作をアダプターのコンシューマーによって選択に基づく (受信シナリオ) 用サービス。 場合でも、アダプターのコンシューマーがツールを使用することをお勧め[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]([!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk アプリケーションが発生した場合)、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]パブリック インターフェイスを提供`Microsoft.ServiceModel.Channels.MetadataRetrievalClient.GetMetadata%2A`を取得しますSystem.Web.Services.Description.ServiceDescription、Web サービス記述言語 (WSDL) 選択した操作と型に関する情報を含むを表します。 アダプター ライターのためのメタデータ オブジェクト モデルの使用、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]から派生したクラスを含む`Microsoft.ServiceModel.Channels.Common.OperationMetadata`と`Microsoft.ServiceModel.Channels.Common.TypeMetadata`を各操作と種類の詳細を記述します。  
  