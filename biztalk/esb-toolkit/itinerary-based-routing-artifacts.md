---
title: "行程ベースのルーティング アイテム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cff38ab7-5a16-42cc-9065-075e9db7acd3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca01cc5313c8ca64418f65cec3fdf18fdbc85df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing-artifacts"></a>行程ベースのルーティング コンポーネント
行程ベースのルーティング機能、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]複数のアセンブリで定義されているキーの成果物のセットが含まれます。 次の表を操作するときの開発者と追加の ESB itinerary サービス実装と旅程ベースのルーティング実装を拡張するためのカテゴリによってこれらの成果物が一覧表示します。  
  
## <a name="esb-itinerary-classes"></a>ESB Itinerary クラス  
 次の表には、アセンブリと、ESB に含まれるアイテムが一覧表示します。道順のプロジェクトです。 格納しているアセンブリの名前は**Microsoft.Practices.ESB.Itinerary.dll**です。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|**MessageHelper**|すべてプライベート関数が呼び出した他のプロジェクトの成果物が含まれています。|  
|**IItineraryStep**|返される、パブリック クラス、 **GetItineraryStep**メソッドです。|  
|**ResolverCollection**|サービスに関連付けられている競合回避モジュールをすべてのコレクションを実装します。 このクラスは、によって公開される、 **IItineraryStep**インターフェイスし、によって設定されますが、 **GetItineraryStep**メソッド。|  
|**IMessagingService**|メッセージ ベースの itinerary サービスによって実装されるインターフェイスを定義します。|  
|**IMessagingService**|作成するためのファクトリ**IMessagingService** Esb.config で構成された名前に基づいてオブジェクト。|  
  
## <a name="esb-itinerary-messaging-services"></a>ESB Itinerary メッセージング サービス  
 次の表で定義されたクラス、 **Microsoft.Practices.ESB.Itinerary.Services.dll**内のアセンブリ**Microsoft.Practices.ESB.Itinerary.Services**名前空間。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|**ルーティング**|ESB itinerary メッセージングのルーティングの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャーの逆アセンブル コンポーネントによって呼び出されます。|  
|**変換**|ESB 行程がメッセージング変換サービスの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャーの逆アセンブル コンポーネントによって呼び出されます。|  
  
 次の表に含まれるアイテムの一覧、 **Microsoft.Practices.ESB.Itinerary.Services.Broker.dll**アセンブリ。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|**MessagingBroker**|ESB 行程がメッセージングのメッセージ コンテキストでルーティング サービスの実装: Esb.config ファイルを使用して ESB ディスパッチャーまたはディスパッチャーの逆アセンブル コンポーネントによって呼び出されます。|  
  
 これらのサービスは、BizTalk ESB Toolkit の構成ファイル、Esb.config でも定義されます。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB Itinerary オーケストレーション サービス  
 次の表に含まれるアイテムの一覧、 **Microsoft.Practices.ESB.Agents.dll**アセンブリ。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|Delivery.odx|ルーティング オーケストレーション itinerary サービスのサービス名で識別されるサンプル**Microsoft.Practices.ESB.Services.Routing**です。|  
|Transform.odx|サンプル変換オーケストレーション itinerary サービス、サービス名で識別される**Microsoft.Practices.ESB.Services.Transform**です。|  
  
## <a name="esb-itinerary-pipeline-components"></a>ESB Itinerary パイプライン コンポーネント  
 次の表に、アセンブリとの成果物が含まれている、 **Microsoft.Practices.ESB.Itinerary.PipelineComponents.dll**アセンブリ。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|**行程**|処理および受信メッセージの日程を検証するプライマリの itinerary 処理パイプライン コンポーネントです。|  
|**ItineraryCache**|送信請求-応答送信ポートで使用するため itinerary キャッシュ パイプライン コンポーネント。|  
|**ItinerarySelector**|ランプでの汎用のサーバー側の日程を解決する itinerary セレクター パイプライン コンポーネント。|  
  
## <a name="esb-itinerary-pipelines"></a>ESB Itinerary パイプライン  
 次の表に、アセンブリとの成果物が含まれている、 **Microsoft.Practices.ESB.Itinerary.Pipelines.dll**アセンブリ。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|ItineraryReceive|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信と受信場所のパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB 行程、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItineraryReceivePassthrough||  
|ItineraryReceiveXml|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信、受信メッセージを複数のエンドポイントにルーティングする受信場所のパイプラインし、次のパイプライン コンポーネントが含まれていますを使用します。<br /><br /> ESB 行程、ESB ディスパッチャーの逆アセンブラー|  
|ItinerarySend|行程出口で使用される itinerary パイプラインです。 送信ポート、送信ポートのパイプラインし、次のパイプライン コンポーネントを含むよう使用します。<br /><br /> ESB ディスパッチャー、XML アセンブラー ESB Itinerary キャッシュ|  
|ItinerarySendPassthrough|行程出口で使用される itinerary パイプラインです。 送信ポート、送信ポートのパイプラインし、次のパイプライン コンポーネントを含むよう使用します。<br /><br /> ESB ディスパッチャー、ESB Itinerary キャッシュ|  
|ItinerarySendReceive|行程出口で使用される itinerary パイプラインです。 送信請求-応答の受信パイプラインが送信ポートと、次のパイプライン コンポーネントが含まれていますを使用します。<br /><br /> ESB Itinerary キャッシュ、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItineraryForwarderSendReceive|行程出口で使用される itinerary パイプラインです。 受信と送信ポートのパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB Itinerary キャッシュ、XML 逆アセンブラー、ESB ディスパッチャー、フォワーダー|  
|ItineraryForwarderSendReceiveXml|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信と送信ポートのパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB Itinerary キャッシュ、ESB ディスパッチャーを逆アセンブルするフォワーダー|  
|ItinerarySelectReceive|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信と受信場所のパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB Itinerary セレクター、XML 逆アセンブラー、ESB ディスパッチャー|  
|ItinerarySelectReceivePassthrough|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信と受信場所のパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB Itinerary セレクター、ESB ディスパッチャー|  
|ItinerarySelectReceiveXml|行程 Web サービスで-ランプで使用される itinerary パイプラインです。 受信と受信場所のパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> XML 逆アセンブラー、ESB Itinerary セレクター、ESB ディスパッチャー|  
|ItinerarySelectSendReceive|行程出口で使用される itinerary パイプラインです。 受信と送信ポートのパイプラインが、次のパイプライン コンポーネントが含まれています、使用します。<br /><br /> ESB Itinerary キャッシュ、ESB Itinerary セレクター、XML 逆アセンブラー、ESB ディスパッチャー|  
  
## <a name="esb-itinerary-schemas"></a>ESB Itinerary スキーマ  
 次の表に、アセンブリとの成果物が含まれている、 **Microsoft.Practices.ESB.Itinerary.Schemas.dll**アセンブリ。  
  
|キーの成果物|Description|  
|------------------|-----------------|  
|Itinerary.xsd|Windows Communication Foundation WCF ベースし、SOAP に基づく Web サービス上のランプで使用される ESB itinerary SOAP ヘッダーを定義します。|  
|ItineraryDescription.xsd|この scehma は itinerary 参照データを表すし、WCF ベースでの傾斜するメッセージを送信するために使用する必要があります。|  
|システム Properties.xsd|ESB 行程に関連する BizTalk コンテキスト プロパティを定義します。|