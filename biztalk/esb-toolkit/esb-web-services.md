---
title: ESB Web サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c122ecdd-344a-4f76-9c73-bf692d479c09
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1b2f6bc30982ea05717fd8e151997e2a3f90a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973363"
---
# <a name="esb-web-services"></a>ESB Web サービス
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の Web サービスが含まれています。  
  
- <strong>スケジュール オンランプ ランプで Web サービス。</strong>これらのサービスは、外部メッセージを受け入れるし、処理のためのメッセージを送信します。 日程の内容は、実行するサービスを記述するメタデータと処理の手順を説明します。 ルーティング サービスをメッセージのルーティング、変換サービスがメッセージを変換する方法を指定するエンドポイントを定義します。 これらのサービス処理をサポート一方向と双方向の両方 (要求-応答)。ASMX と Windows Communication Foundation (WCF) の両方の実装が提供されます。 旅行プラン Web サービスは、任意のメッセージ型を受け入れるために、それぞれの種類のメッセージではありません。  
  
- <strong>リゾルバー Web サービス。</strong>このサービスにより、外部のアプリケーションを競合回避モジュールのフレームワークでサポートされている解決メカニズムに基づく ESB エンドポイントを検索するには、Microsoft ESB リゾルバー Framework を呼び出します。 サービスでは、ASMX と WCF の両方の実装も提供します。  
  
- <strong>Web サービスを変換します。</strong>このサービスでは、Microsoft BizTalk Server の実行がマップの実行は BizTalk Server に基づいていないアプリケーションを BizTalk Server の機能を拡張する、メッセージ ボックスの永続化のオーバーヘッドなしにマップします。 サービスは、ASMX と WCF の両方の実装を提供します。  
  
- <strong>例外処理の Web サービス。</strong>このサービスは、外部ソースからの例外メッセージを受け入れると、エラー プロセッサ パイプラインを使用してルートは正規化、追跡、および例外メッセージを ESB 管理ポータルに公開します。 サービスは、ASMX と WCF の両方の実装を提供します。  
  
- <strong>UDDI の Web サービスです。</strong>このサービスにより、サービス名、ビジネス プロバイダー、またはビジネス カテゴリに基づいて、エンドポイントを検索するには、アプリケーションとユーザー、アプリケーションとユーザー、ビジネスのプロバイダー、サービスを操作することもできます; に格納されているカテゴリと、UDDI のリポジトリ。 ESB 管理ポータルおよびサード パーティ プロバイダーによって使用されるキーのインフラストラクチャ サービスです。  
  
- <strong>BizTalk 操作 Web サービスです。</strong>この ASMX ベースのサービスは、BizTalk Server ホスト、オーケストレーション、アプリケーション、およびユーザーとサード パーティ内のコンピューターの場所に関係なく、アプリケーションとホストの状態を簡単にクエリを有効にすると、状態に関する情報を公開します。BizTalk Server グループ。 クエリには、メッセージの状態とフロー、状態の変更、現在のサービス インスタンスおよびメッセージの詳細を含めることができます。 サービスを更新できますも受信場所。 ESB 管理ポータルおよびサード パーティ プロバイダーによって使用されるキーのインフラストラクチャ サービスです。  
  
  一部として提供される Web サービスの詳細については、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を参照してください[BizTalk ESB Toolkit Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)します。