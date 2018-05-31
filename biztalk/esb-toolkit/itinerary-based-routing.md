---
title: 行程ベースのルーティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fbfe8877202a2f691bd30fd2b56fc3032240ee9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294514"
---
# <a name="itinerary-based-routing"></a>行程ベースのルーティング
コア機能の 1 つ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]はエンタープライズ レベルのメッセージング アプリケーションの開発を簡略化し、多数の静的なを維持するためのコストを削減する行程ベースのルーティングのプロビジョニングの送信ポートと受信場所。  
  
 (これは、ルーティング、変換、およびカスタムのサービスを含めることができます) を実行するサービスの一覧および各サービスの実行に必要なメタデータを解決するのには必要な構成情報の日程で構成されます。 たとえば、旅行計画の 1 つの段階は、ルーティング サービス可能性があります。このサービスに関連付けられている解像度の手順については、特定のターゲット エンドポイントはルーティング Universal Description、検出、および Integration (UDDI) またはビジネス ルール エンジン (BRE) を参照するサービスを指示可能性があります。メッセージ。  
  
 行程は、次のように、受信メッセージに添付できます。  
  
-   クライアントによって送信されるメッセージに行程に関連するデータが含まれていません。 受信パイプラインを解決するには、取得、およびメッセージの内容またはコンテキストに基づいて適切な旅程をアタッチします。  
  
-   クライアントによって送信されるメッセージには、ビジネス アクティビティ監視 (BAM) 追跡の一意の識別子だけでなく、itinerary 名とバージョンを含む itinerary 参照データを定義する SOAP ヘッダーを含めることができます。 受信パイプラインは、この情報を評価し、ESBItineraryDb データベースから適切な旅程を取得します。  
  
-   クライアントによって送信されるメッセージには、旅行計画の内容全体を含む itinerary は SOAP ヘッダーを持つことができます。 この設計はお勧めできませんテスト目的でのみ使用する必要があります。  
  
 日程が受信メッセージの解決した後、受信パイプラインは itinerary データにこのメッセージをサブスクライブする任意の Microsoft BizTalk Server コンポーネントがアクセスして使用可能なプロパティをし、それによって、メッセージ コンテキストに昇格させます。 BizTalk Server コンポーネントでは、現在の itinerary ステップの詳細を取得、必要な処理を完了、および次の手順に旅行計画を進めることができます。 これにより、次のサービス内、メッセージの処理に旅行計画に従って、発行-BizTalk Server の機能をサブスクライブします。  
  
 ESB の動的な解決メカニズム、変換、itinerary の処理、およびメッセージの作成については、次を参照してください。[主要なシナリオと開発タスク](../esb-toolkit/key-scenarios-and-development-tasks.md)です。