---
title: "主要なコンポーネントの WCF LOB Adapter SDK |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59b8029b-4799-471b-8825-15d79a30bf1f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c034c1006ed898a28aab04cde201524e4c3b13b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="key-components-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の主要なコンポーネント
使用して、アダプターの開発、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]の多くは、次の基本的なコンポーネントの使用が必要です。  
  
-   **接続コンポーネント**を確立し、基幹業務システムへの接続を維持するためにします。  
  
-   **ハンドラー コンポーネント**を定義し、受信および送信メッセージと操作のメタデータを操作するための手順を実装します。  
  
-   **メタデータ コンポーネント**を定義し、基幹業務システムとの通信に使用されるメタデータを操作します。  
  
-   **カスタム コンポーネント**トランザクション、信頼できるメッセージング、およびセキュリティのサポートを提供します。  
  
-   **コア コンポーネント**結び付け、すべてのコンポーネントをシームレスに統合を確認してください。[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。  
  
 これらのコンポーネントは、このトピックの中心です。  
  
## <a name="connection-components"></a>接続コンポーネントには  
 接続のコンポーネントにはインターフェイスが含まれてし、支援するクラスを定義し、接続の有効期間を制御だけでなく統一リソース識別子 (URI) クエリの属性およびユーザー属性を管理します。、 接続コンポーネントには、インターフェイスと、次の表で説明されているクラスが含まれます。  
  
|接続コンポーネント|必須/省略可能|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|必須|アダプターを使用するユーザーのエクスペリエンスを作成、カスタマイズされた URI を提供するための基本クラスです。|  
|`Microsoft.ServiceModel.Channels.Common.IConnection`|必須|接続の動作を定義するインターフェイスです。 開発者は、ターゲット システムに接続を定義するには、このインターフェイスを実装する必要があります。|  
|`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`|必須|接続ファクトリの基本クラス。 開発者は、ターゲット システムの接続ファクトリを定義するときのサブクラスです。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`|省略可|接続プールの動作を制御する設定が含まれています。 開発者は、ターゲット システムの動作に基づいてこれらの値を調整することがあります。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`|省略可|接続プールの動作を制御する静的な設定が含まれています。 開発者は、そのターゲット システムにこれらの値を調整することがあります。|  
  
 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]の実装が作成されます`Microsoft.ServiceModel.Channels.Common.IConnection``Microsoft.ServiceModel.Channels.Common.ConnectionUri`と`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`ウィザード オプションの選択に関係なく。 これらの実装しますが、含まれる (接続 URI の接続のプロパティを含む)、ウィザードで選択したオプションをサポートするためのコード、アダプター開発者は、開く、閉じるおよびその他のメソッドの実装を提供する必要がある`Microsoft.ServiceModel.Channels.Common.IConnection`と`Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  
  
## <a name="handler-components"></a>ハンドラー コンポーネント  
 ハンドラー コンポーネントを含め、さまざまなメッセージ交換パターンの受信のサポート、送信、非同期の受信、非同期送信、およびメタデータの検索、参照、および操作を解決します。 ハンドラー コンポーネントには、インターフェイスと、次の表で説明されているクラスが含まれます。  
  
|ハンドラー コンポーネント|必須/省略可能|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|省略可|ターゲット システムからメッセージを非同期的に受信するために使用します。 非同期のサポートはオプションです。|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|省略可|ターゲット システムからメッセージを非同期的に送信するために使用します。 非同期のサポートはオプションです。|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|省略可|ターゲット システムからメッセージを受信するために使用します。 開発者は、アダプターは、対象システムからメッセージをリッスンする必要がある場合、このハンドラーを実装する必要があります。|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|省略可|ターゲット システムにメッセージを送信するためのサポートを提供します。 省略可能で、中に、要求-応答メッセージ パターン必要があります。 最も基本的な通信テクノロジは、HTTP、RPC、およびその他の多くを含むこのパターンに基づいています。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|省略可|このハンドラーは、アダプター メタデータの参照をサポートしている場合に実装します。 オプションですが、開発者は多くの場合、ターゲット システムで使用できる操作の一覧を提供するには、このハンドラーを実装します。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|省略可|アダプターを取得し、システムに固有のロジックとデータ型を表す対象システムからメタデータを返すときに、このハンドラーを実装する必要があります。 実際のターゲット システムからメタデータを取得できるまたは、ターゲット システムの機能を表す作成できます。 たとえば、FTP アダプターを作成 GET および PUT 操作します。<br /><br /> 必須ではありません、開発者は一般に、特定の操作に関する情報を提供するには、このハンドラーを実装します。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|省略可|このハンドラーは、アダプター メタデータの検索をサポートしている場合に実装します。|  
  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装が作成されます`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`、 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`と、開発者によってなされた選択に基づくメタデータ ハンドラー。 サポート コードを提供します。ただし、アダプター開発者は、開始し、受信のリスナーを停止するためのコードと TODO コメントでマークされているその他のコードを指定する必要があります。  
  
## <a name="metadata-components"></a>メタデータ コンポーネント  
メタデータ コンポーネントは、メタデータ要求を処理し、種類と、対象アプリケーションで操作を記述するために、サポートを提供します。 ハンドラーは、コンポーネントは、メタデータ要求に対処する方法を制御します。 メタデータ コンポーネントは、データ型と、ターゲット システムで公開される操作について説明します。  

 メタデータ コンポーネントは 2 種類のメタデータ情報を保持するために設計されています。 メタデータとメタデータの操作を入力します。  
  
-   *入力メタデータ*ターゲット システムで使用できるデータ型について説明し、単純な XSD スキーマ型または複合型であるかどうかと、配列である場合、型、配列のプロパティの名前が含まれています。  
  
-   *メタデータ操作*ターゲット システムで使用できる操作について説明します。 プロパティには、戻り値の型、パラメーター、および操作名の一覧が含まれます。  
  
 アダプターでメタデータのサポートは省略可、ただし推奨です。 使用する利点の 1 つ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]としての機能を実装すると、アダプターを構築する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスが公開して、動的な一連の操作にバインドする機能。  

> [!NOTE]
>  制限付きの静的メソッドのセットを公開する必要がある場合は、使用を検討する必要があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。  
 
  コンポーネントを処理するために使用できる、記述、およびメタデータ操作は、次の表に記載されています。  
  
|メタデータ コンポーネント|Description|  
|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`|アダプターの複雑な修飾の型を表すクラスです。 たとえば、対象システムは、リレーショナル データベース、テーブル、行、またはユーザー定義のプロシージャが型を返す場合すべてありますカスタム修飾型。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|ターゲット システムのメタデータの操作を表す基本クラスです。 たとえば、サブクラス OperationMetadata アダプターに、リレーショナル データベースを対象とするストアド プロシージャに関する情報が含まれる可能性があります。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadataTraceRecord`|トレース ファイルにメタデータの操作をキャプチャする手段を提供します。 トレースは、一意の ID、最後にアクセスするには、timestamp、表示名、元の名前、パラメーター、およびその他の詳細などの情報を収集します。|  
|`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`|パラメーターと戻り値の型などの操作の属性を定義する手段を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameter`|ターゲット システムでは操作を呼び出すに使用するパラメーターについて説明します。 プロパティには、名前、元の名前、パラメーターの方向、およびパラメーターが空かどうかどうかを示すフラグが含まれます。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameterDirection`|操作のパラメーターの方向を示す列挙型。 パラメーターは、のみ (In)、送信のみ (アウト)、または双方向 (InOut) バインドされていることができます。|  
|`Microsoft.ServiceModel.Channels.Common.OperationResult`|操作結果を表します。 Void 型または null を返す操作、文字列、整数、または操作に応じて他の値の OperationResult.Empty を使用できます。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedType`|基本クラス型のプロパティを修飾し、ターゲット システムの型のメタデータのプロパティを記述するために使用するよう設計されています。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedTypeContainer`|関連する修飾型のセットのコンテナーを提供します。|  
|`Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`|その型が W3C XSD スキーマの種類に直接マップ時に、ターゲット システムの型のメタデータのプロパティを示します。 使用可能な型の一覧は、次を参照してください。 [XmlTypeCode 列挙](https://msdn.microsoft.com/library/system.xml.schema.xmltypecode(v=vs.110).aspx)です。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMember`|構造化された型のメタデータに、単純または複雑なデータ メンバーを定義する方法を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadata`|ターゲット システムの種類のメタデータを表す基本クラスです。|  
|`Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`|複雑なまたは単純型のメンバーを格納するデータ構造体を定義する方法を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataCollection`|関連する型のメタデータのセットのコンテナーを提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataTraceRecord`|トレース ファイルに型のメタデータをキャプチャする手段を提供します。 トレースは、一意の ID などの情報を収集、最後にアクセスした時刻、タイムスタンプ、およびその他の詳細。|  
  
## <a name="custom-components"></a>カスタム コンポーネント  
 カスタム コンポーネントは、トランザクション、セキュリティ、信頼性の高いメッセージングとは、ターゲット システムに大きく依存するその他の機能のサポートを提供します。 使用して、アダプター開発者として、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、ターゲット システムの機能を理解して、それらをサポートする範囲を判断する必要があります。  
  
## <a name="core-components"></a>コア コンポーネント  
 コア コンポーネントに接続するアダプターを有効にする基本クラスとインターフェイスのセットを提供する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]です。 コア コンポーネントは、次の表で説明します。  
  
|コア コンポーネント|必須/省略可能|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.Adapter`|必須|使用して作成されたアダプターの基本クラス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]です。 対話を[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ|  
|`Microsoft.ServiceModel.Channels.Common.AdapterBinding`|必須|アダプターの接続プールなどのさまざまな設定を制御する設定を含むクラス (`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`)、キャッシュ (`Microsoft.ServiceModel.Channels.Common.CacheSettings`)、メタデータ (`Microsoft.ServiceModel.Channels.Common.MetadataSettings`)、およびメッセージング (`Microsoft.ServiceModel.Channels.Common.MessagingSettings`)。|  
  
 カスタム アダプターは、WCF バインディングを介して公開されます。 詳細については、WCF のマニュアルを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=100308](http://go.microsoft.com/fwlink/?LinkId=100308)です。  
  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装を作成する`Microsoft.ServiceModel.Channels.Common.Adapter`、 `Microsoft.ServiceModel.Channels.Common.AdapterBinding`、 `System.ServiceModel.Configuration.StandardBindingElement`、および`System.ServiceModel.Configuration.StandardBindingCollectionElement`アダプター システムにバインディングを WCF 構成を公開します。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装も生成されます`System.ServiceModel.Configuration.BindingElementExtensionElement`を有効にする`Microsoft.ServiceModel.Channels.Common.Adapter`コンピューターまたはアプリケーション構成ファイルからの WCF カスタム バインド内で使用します。  
  
 StandardBindingElement、StandardBindingCollectionElement、および BindingElementExtensionElement に関する詳細については、WCF のドキュメントを参照してください。  
  
 記述されたアダプターの構成の詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください[WCF LOB アダプター SDK を使用して、アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)です。  
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して LOB システムを理解します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)