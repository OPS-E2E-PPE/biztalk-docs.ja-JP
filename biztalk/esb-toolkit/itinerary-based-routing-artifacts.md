---
title: スケジュールに基づくルーティング アイテム |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff38ab7-5a16-42cc-9065-075e9db7acd3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c690d4157166db18fb29466d9d64283d892ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261566"
---
# <a name="itinerary-based-routing-artifacts"></a>スケジュールに基づくルーティング アイテム
ルーティング機能をスケジュールに基づく、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]な複数のアセンブリで定義されているキーの成果物セットが含まれます。 次の表に、これらの成果物を開発者が使用する場合、および実装を拡張する、スケジュールに基づくルーティング ESB スケジュール サービスの追加の実装で支援するカテゴリにします。  
  
## <a name="esb-itinerary-classes"></a>ESB スケジュール オンランプ クラス  
 次の表には、アセンブリと、ESB に含まれるアイテムが一覧表示します。スケジュール オンランプ プロジェクトです。 格納しているアセンブリの名前は**Microsoft.Practices.ESB.Itinerary.dll**します。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|**Messagehelper 参照**|その他のプロジェクトの成果物によって呼び出されたすべてのプライベート関数が含まれています。|  
|**IItineraryStep**|返されるパブリック クラス、 **GetItineraryStep**メソッド。|  
|**ResolverCollection**|サービスに関連付けられている競合回避モジュールをすべてのコレクションを実装します。 このクラスは、によって公開される、 **IItineraryStep**インターフェイスし、設定が、 **GetItineraryStep**メソッド。|  
|**IMessagingService**|スケジュール サービスとしてメッセージング ベースによって実装されるインターフェイスを定義します。|  
|**IMessagingService**|作成するためのファクトリ**IMessagingService** Esb.config で構成された名前に基づいてオブジェクト。|  
  
## <a name="esb-itinerary-messaging-services"></a>ESB スケジュール メッセージング サービス  
 次の表で定義されているクラス、 **Microsoft.Practices.ESB.Itinerary.Services.dll**でアセンブリ**Microsoft.Practices.ESB.Itinerary.Services**名前空間。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|**ルーティング**|ESB スケジュール メッセージングのルーティングの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャー逆アセンブルするコンポーネントによって呼び出されます。|  
|**変換**|ESB 行程がメッセージング変換サービスの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャー逆アセンブルするコンポーネントによって呼び出されます。|  
  
 次の表に含まれるアイテムの一覧、 **Microsoft.Practices.ESB.Itinerary.Services.Broker.dll**アセンブリ。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|**MessagingBroker**|ESB 行程がメッセージングのメッセージ コンテキストで、ルーティング サービスの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャー逆アセンブルするコンポーネントによって呼び出されます。|  
  
 これらのサービスは、BizTalk ESB Toolkit の構成ファイル、Esb.config でも定義されます。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB スケジュール オンランプ オーケストレーション サービス  
 次の表に含まれるアイテムの一覧、 **Microsoft.Practices.ESB.Agents.dll**アセンブリ。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|Delivery.odx|ルーティング オーケストレーション スケジュール サービスのサービス名で識別されるサンプル**Microsoft.Practices.ESB.Services.Routing**します。|  
|Transform.odx|サンプル変換オーケストレーション スケジュール サービスをサービス名で識別される**Microsoft.Practices.ESB.Services.Transform**します。|  
  
## <a name="esb-itinerary-pipeline-components"></a>ESB スケジュール オンランプ パイプライン コンポーネント  
 次の表に、アセンブリと成果物に含まれる、 **Microsoft.Practices.ESB.Itinerary.PipelineComponents.dll**アセンブリ。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|**旅行プラン**|処理および受信メッセージの旅行プランを検証します。 プライマリ スケジュール オンランプ処理パイプライン コンポーネント。|  
|**ItineraryCache**|送信請求-応答で使用するためのスケジュール キャッシュ パイプライン コンポーネントは、ポートを送信します。|  
|**ItinerarySelector**|グラデーションでの汎用のサーバー側のスケジュールを解決するスケジュール セレクターのパイプライン コンポーネント。|  
  
## <a name="esb-itinerary-pipelines"></a>ESB スケジュール オンランプ パイプライン  
 次の表に、アセンブリと成果物に含まれる、 **Microsoft.Practices.ESB.Itinerary.Pipelines.dll**アセンブリ。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|ItineraryReceive|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 受信の受信場所のパイプラインし、次のパイプライン コンポーネントが含まれていますが使用されます。<br /><br /> ESB スケジュール、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItineraryReceivePassthrough||  
|ItineraryReceiveXml|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 使用、受信、受信メッセージを複数のエンドポイントにルーティングする受信場所のパイプラインし、次のパイプライン コンポーネントが含まれています。<br /><br /> ESB スケジュール、ESB ディスパッチャー逆アセンブラー|  
|ItinerarySend|スケジュールの無効-ランプで使用されるスケジュール オンランプ パイプラインです。 送信ポート、送信ポートのパイプラインし、次のパイプライン コンポーネントを含む、使用します。<br /><br /> ESB ディスパッチャー、XML アセンブラーでは、ESB スケジュール キャッシュ|  
|ItinerarySendPassthrough|スケジュールの無効-ランプで使用されるスケジュール オンランプ パイプラインです。 送信ポート、送信ポートのパイプラインし、次のパイプライン コンポーネントを含む、使用します。<br /><br /> ESB ディスパッチャー、ESB スケジュール キャッシュ|  
|ItinerarySendReceive|スケジュールの無効-ランプで使用されるスケジュール オンランプ パイプラインです。 送信請求-応答の受信パイプラインが送信ポートと、次のパイプライン コンポーネントが含まれていますが使用されます。<br /><br /> ESB スケジュール キャッシュ、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItineraryForwarderSendReceive|スケジュールの無効-ランプで使用されるスケジュール オンランプ パイプラインです。 使用、受信、送信ポートのパイプラインし、次のパイプライン コンポーネントが含まれています。<br /><br /> ESB スケジュール キャッシュ、XML 逆アセンブラー、ESB ディスパッチャー、フォワーダー|  
|ItineraryForwarderSendReceiveXml|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 使用、受信、送信ポートのパイプラインし、次のパイプライン コンポーネントが含まれています。<br /><br /> ESB スケジュール キャッシュ、ESB ディスパッチャー逆アセンブル、フォワーダー|  
|ItinerarySelectReceive|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 受信の受信場所のパイプラインし、次のパイプライン コンポーネントが含まれていますが使用されます。<br /><br /> ESB スケジュール セレクター、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItinerarySelectReceivePassthrough|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 受信の受信場所のパイプラインし、次のパイプライン コンポーネントが含まれていますが使用されます。<br /><br /> ESB スケジュール セレクター、ESB ディスパッチャー|  
|ItinerarySelectReceiveXml|旅行プランの Web サービスに着手で使用されるスケジュール オンランプ パイプラインです。 受信の受信場所のパイプラインし、次のパイプライン コンポーネントが含まれていますが使用されます。<br /><br /> XML 逆アセンブラー、ESB スケジュール セレクター、ESB ディスパッチャー|  
|ItinerarySelectSendReceive|スケジュールの無効-ランプで使用されるスケジュール オンランプ パイプラインです。 使用、受信、送信ポートのパイプラインし、次のパイプライン コンポーネントが含まれています。<br /><br /> ESB スケジュール キャッシュ、ESB スケジュール セレクター、XML 逆アセンブラー、ESB ディスパッチャー|  
  
## <a name="esb-itinerary-schemas"></a>ESB スケジュール スキーマ  
 次の表に、アセンブリと成果物に含まれる、 **Microsoft.Practices.ESB.Itinerary.Schemas.dll**アセンブリ。  
  
|キーの成果物|説明|  
|------------------|-----------------|  
|Itinerary.xsd|Windows Communication Foundation の WCF ベースし、SOAP ベース Web サービス オンランプで使用される ESB オンランプ SOAP ヘッダーを定義します。|  
|ItineraryDescription.xsd|このスキーマは、スケジュールの参照データを表し、WCF ベースでの機能を増強するメッセージを送信するために使用する必要があります。|  
|システム Properties.xsd|ESB スケジュールに関連する BizTalk コンテキスト プロパティを定義します。|