---
title: 主要なコンポーネントの WCF LOB Adapter SDK |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59b8029b-4799-471b-8825-15d79a30bf1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d033e452c4f67b66ed7e3b50b2c553def558015
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972235"
---
# <a name="key-components-of-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK の主要なコンポーネント
アダプターを使用して、開発、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]次の基本的なコンポーネントの多くの使用が必要です。  

- **接続コンポーネント**を確立し、基幹業務システムへの接続を維持します。  

- **ハンドラー コンポーネント**を定義し、受信と送信メッセージとメタデータの操作を使用するために使用する手順を実行します。  

- **メタデータ コンポーネント**定義し、基幹業務システムとの通信に使用されるメタデータを操作します。  

- **カスタム コンポーネント**トランザクション、信頼できるメッセージング、およびセキュリティのサポートを提供します。  

- **コア コンポーネント**結び付け、すべてのコンポーネントをシームレスに統合を確認してください。[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。  

  これらのコンポーネントは、このトピックの中心です。  

## <a name="connection-components"></a>接続のコンポーネント  
 支援するクラスを定義し、接続の有効期間を制御するだけでなく統一リソース識別子 (URI) クエリの属性およびユーザー属性を管理および接続のコンポーネントにはインターフェイスが含まれます。 接続のコンポーネントには、インターフェイスと、次の表で説明されているクラスが含まれます。  

|接続コンポーネント|必須/省略可能|説明|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|必須|アダプターを使用するユーザーのエクスペリエンスを構築、カスタマイズされた URI を提供するための基本クラスです。|  
|`Microsoft.ServiceModel.Channels.Common.IConnection`|必須|接続の動作を定義するインターフェイスです。 開発者は、ターゲット システムに接続を定義するには、このインターフェイスを実装する必要があります。|  
|`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`|必須|接続ファクトリの基本クラス。 開発者は、ターゲット システムの接続ファクトリを定義するときにサブクラスです。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`|省略可|接続プールの動作を制御する設定が含まれています。 開発者は、ターゲット システムの動作に基づいてこれらの値を調整することがあります。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`|省略可|接続プールの動作を制御する静的な設定が含まれています。 開発者は、そのターゲット システムにこれらの値を調整することがあります。|  

 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]の実装を作成`Microsoft.ServiceModel.Channels.Common.IConnection``Microsoft.ServiceModel.Channels.Common.ConnectionUri`と`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`ウィザード オプションの選択に関係なく。 これらの実装には (接続 URI の接続のプロパティを含む)、ウィザードで選択したオプションをサポートするためのコードが含まれて、アダプター開発者が開く、閉じるおよびその他のメソッドの実装を提供する必要がありますが、`Microsoft.ServiceModel.Channels.Common.IConnection`と`Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  

## <a name="handler-components"></a>ハンドラー コンポーネント  
 ハンドラー コンポーネントが異なるメッセージ交換パターンを含む受信のサポートを提供、送信、非同期受信を非同期送信、およびメタデータの検索、参照、および操作を解決します。 ハンドラー コンポーネントには、インターフェイスと、次の表で説明されているクラスが含まれます。  

|ハンドラー コンポーネント|必須/省略可能|説明|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|省略可|ターゲット システムから非同期的にメッセージを受信するために使用します。 非同期のサポートは、省略可能です。|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|省略可|ターゲット システムからメッセージを非同期的に送信するために使用します。 非同期のサポートは、省略可能です。|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|省略可|ターゲット システムからメッセージを受信するために使用します。 開発者は、アダプターは、ターゲット システムからのメッセージをリッスンする必要がある場合、このハンドラーを実装する必要があります。|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|省略可|ターゲット システムにメッセージを送信するためのサポートを提供します。 省略可能な中には、要求-応答のメッセージ パターン必要があります。 最も基本的な通信テクノロジは、HTTP、RPC、およびその他の多くを含むこのパターンに基づいています。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|省略可|アダプター メタデータの参照をサポートしている場合、このハンドラーが実装されます。 オプションですが、開発者は多くの場合、ターゲット システムで使用できる操作の一覧を提供するには、このハンドラーを実装します。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|省略可|アダプターを取得し、システム固有のロジックとデータ型を表すターゲット システムからメタデータを返しますと、このハンドラーを実装する必要があります。 メタデータは、実際のターゲット システムから取得できますか、ターゲット システムの機能を表すために作成できます。 たとえば、FTP アダプターを作成 GET および PUT 操作。<br /><br /> ため必要はありませんが、開発者は一般に、特定の操作に関する情報を提供するには、このハンドラーを実装します。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|省略可|アダプター メタデータの検索をサポートしている場合、このハンドラーが実装されます。|  

 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装を作成`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`、 `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`、`Microsoft.ServiceModel.Channels.Common.IInboundHandler`と、開発者が行う選択に基づくメタデータ ハンドラー。 サポート コードが提供されます。ただし、アダプター開発者は、開始および受信のリスナーを停止するコードと TODO コメントでマークされているその他のコードを指定する必要があります。  

## <a name="metadata-components"></a>メタデータ コンポーネント  
メタデータ コンポーネントは、メタデータの要求を処理するため、型と、ターゲット アプリケーションでの操作を記述するために、サポートを提供します。 ハンドラー コンポーネントでは、メタデータの要求の処理方法を制御します。 メタデータ コンポーネントは、データ型と、ターゲット システムで公開される操作について説明します。  

 メタデータ コンポーネントが 2 種類のメタデータ情報を保持するために設計されています: メタデータとメタデータの操作を入力します。  

- *入力メタデータ*ターゲット システムで利用できるデータ型について説明し、単純な XSD スキーマ型または複合型であるかどうかと、配列である場合、型、その配列プロパティの名前が含まれています。  

- *メタデータ操作*ターゲット システムで利用できる操作について説明します。 プロパティには、戻り値の型、パラメーター、および操作名の一覧が含まれます。  

  アダプターでメタデータのサポートは、省略可、ただし推奨されるは。 使用する利点の 1 つ、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]としての機能を実装すると、アダプターを構築する、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]サービスが公開して、動的な一連の操作にバインドする機能。  

> [!NOTE]
>  限られた一連の静的メソッドを公開する必要がある場合は、使用を検討する必要があります、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。  

  処理のために使用できる、コンポーネント、記述して、メタデータの操作は、次の表で説明されています。  

|メタデータ コンポーネント|説明|  
|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`|アダプターの複雑な修飾の型を表すクラス。 たとえば、ターゲット システムは、リレーショナル データベース、テーブル、行、またはユーザー定義のプロシージャが型を返す場合可能性がありますすべて可能なカスタム修飾型。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|ターゲット システムの操作のメタデータを表す基本クラスです。 たとえば、サブクラス OperationMetadata リレーショナル データベースを対象とするアダプターでのストアド プロシージャに関する情報が含まれる可能性があります。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadataTraceRecord`|トレース ファイルにメタデータの操作をキャプチャする手段を提供します。 トレースは、一意の ID、最後にアクセスすると、タイムスタンプ、表示名、元の名前、パラメーター、およびその他の詳細などの情報を収集します。|  
|`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`|パラメーターと戻り値の型などの操作の属性を定義する方法を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameter`|ターゲット システムの操作を呼び出すに使用されるパラメーターについて説明します。 プロパティには、名前、元の名前、パラメーターの方向、およびパラメーターが空かどうかどうかを示すフラグが含まれます。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameterDirection`|操作のパラメーターの方向を記述する列挙型。 パラメーターは、のみ (In)、送信のみ (出力)、または双方向 (InOut) にバインドされていることができます。|  
|`Microsoft.ServiceModel.Channels.Common.OperationResult`|操作の結果を表します。 Void 型または null を返す操作、文字列、整数、または操作によってその他の値に対して OperationResult.Empty ができます。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedType`|基本クラス型のプロパティを修飾し、ターゲット システムの種類のメタデータのプロパティを記述するために使用するように設計します。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedTypeContainer`|一連の関連する修飾型のコンテナーを提供します。|  
|`Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`|その型が W3C XSD のスキーマ型に直接マップ時に、ターゲット システムの種類のメタデータのプロパティを説明します。 使用可能な型の一覧は、[XmlTypeCode 列挙](https://msdn.microsoft.com/library/system.xml.schema.xmltypecode(v=vs.110).aspx)を参照してください。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMember`|構造化型のメタデータに、単純または複雑なデータ メンバーを定義するための手段を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadata`|ターゲット システムの種類のメタデータを表す基本クラスです。|  
|`Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`|複雑なや単純な型のメンバーを含むデータ構造を定義する方法を提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataCollection`|一連の関連する型のメタデータのコンテナーを提供します。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataTraceRecord`|トレース ファイルに型のメタデータをキャプチャする手段を提供します。 最後にアクセスした時刻、タイムスタンプ、およびその他の詳細、トレースは、一意の ID などの情報を収集します。|  

## <a name="custom-components"></a>カスタム コンポーネント  
 カスタム コンポーネントは、トランザクション、セキュリティ、信頼性の高いメッセージング、およびターゲット システムに高度に依存するその他の機能のサポートを提供します。 使用して、アダプター開発者として、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、ターゲット システムの機能を理解し、それらをサポートする範囲を判断する必要があります。  

## <a name="core-components"></a>コア コンポーネント  
 コア コンポーネントに組み込んで、アダプターを有効にする基本クラスとインターフェイスのセットを提供する[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]します。 コア コンポーネントは、次の表で説明します。  


|                     コア コンポーネント                      | 必須/省略可能 |                                                                                                                                                                                          説明                                                                                                                                                                                          |
|---------------------------------------------------------|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `Microsoft.ServiceModel.Channels.Common.Adapter`     | 必須  |                                                      使用して作成されたアダプターの基本クラス、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]します。 対話する責任を負いますが、[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]チャネル アーキテクチャ                                                      |
| `Microsoft.ServiceModel.Channels.Common.AdapterBinding` | 必須  | アダプターの接続プールを含むのさまざまな設定を制御する設定を含むクラス (`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`)、キャッシュ (`Microsoft.ServiceModel.Channels.Common.CacheSettings`)、メタデータ (`Microsoft.ServiceModel.Channels.Common.MetadataSettings`)、およびメッセージング (`Microsoft.ServiceModel.Channels.Common.MessagingSettings`)。 |

 カスタム アダプターは WCF バインドを介して公開されます。 詳細については、WCF ドキュメントを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=100308](http://go.microsoft.com/fwlink/?LinkId=100308)します。  

 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装を作成`Microsoft.ServiceModel.Channels.Common.Adapter`、 `Microsoft.ServiceModel.Channels.Common.AdapterBinding`、 `System.ServiceModel.Configuration.StandardBindingElement`、および`System.ServiceModel.Configuration.StandardBindingCollectionElement`WCF 構成システムへのアダプターのバインドを公開します。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]の実装も生成`System.ServiceModel.Configuration.BindingElementExtensionElement`有効にする`Microsoft.ServiceModel.Channels.Common.Adapter`内のコンピューターまたはアプリケーション構成ファイルから WCF カスタム バインドを使用することです。  

 StandardBindingElement、StandardBindingCollectionElement、および BindingElementExtensionElement の詳細については、WCF のドキュメントを参照してください。  

 作成されたアダプターの構成の詳細については、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を参照してください[WCF LOB アダプター SDK を使用して、アダプターの展開](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)します。  

## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して LOB システムを理解します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)