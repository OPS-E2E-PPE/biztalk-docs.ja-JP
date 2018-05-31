---
title: Web サービスの ESB |Microsoft ドキュメント
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
ms.openlocfilehash: 94e6f59770e14e14ed9599d0c26bae187f340e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294378"
---
# <a name="esb-web-services"></a>ESB Web サービス
[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次の Web サービスが含まれています。  
  
-   **Itinerary 入り口 Web サービスです。** これらのサービスは、外部のメッセージを受け入れるし、処理のためのメッセージを送信します。 日程の内容を実行するサービスを記述するメタデータおよび処理命令が含まれています。 ルーティング サービスは、するメッセージのルーティング変換サービスでは、メッセージを変換する方法を指定するときにエンドポイントを定義します。 これらのサービス処理をサポート一方向と双方向の両方 (要求-応答)。asmx サービスと Windows Communication Foundation (WCF) の両方の実装が提供されます。 行程入り口 Web は、サービスをメッセージの種類の特定、メッセージ型を受け入れるようにします。  
  
-   **競合回避モジュールの Web サービスです。** このサービスは、競合回避モジュールのフレームワークでサポートされている解決メカニズムに基づいて ESB エンドポイントを検索するには、Microsoft ESB リゾルバー Framework を呼び出す外部アプリケーションを使用します。 サービスは、asmx サービスと WCF の両方の実装も提供します。  
  
-   **Web サービスを変換します。** このサービスでは、Microsoft BizTalk Server の実行がマップの実行は BizTalk Server に基づいていませんアプリケーションを BizTalk Server の機能を拡張する、メッセージ ボックスの永続化のオーバーヘッドなしにマップします。 サービスは、asmx サービスと WCF の両方の実装を提供します。  
  
-   **例外処理の Web サービスです。** このサービスは、外部ソースからの例外メッセージを受け入れると、フォールト processor パイプラインを使用してルートは正規化、追跡、および例外のメッセージを ESB 管理ポータルに公開します。 サービスは、asmx サービスと WCF の両方の実装を提供します。  
  
-   **UDDI Web サービスです。** このサービスにより、サービス名、ビジネスのプロバイダー、またはビジネス カテゴリに基づくエンドポイントを検索するには、アプリケーションとユーザー以外の場合はアプリケーションやユーザー、ビジネスのプロバイダー、サービスを操作することもできに格納されているカテゴリ、UDDI のリポジトリ。 これは、ESB の管理ポータルおよびサード パーティ プロバイダーによって使用されるキーのインフラストラクチャ サービスです。  
  
-   **BizTalk Operations Web サービスです。** この ASMX ベースのサービスは、BizTalk Server ホスト、オーケストレーション、アプリケーション、およびユーザーとサード パーティ内のコンピューターの場所に関係なく、アプリケーションとホストの状態を簡単にクエリを有効にすると、状態に関する情報を公開BizTalk Server グループです。 クエリには、メッセージの状態とフロー、状態の変更、現在のサービス インスタンス、およびメッセージの詳細を含めることができます。 サービスを更新できますも受信場所。 これは、ESB の管理ポータルおよびサード パーティ プロバイダーによって使用されるキーのインフラストラクチャ サービスです。  
  
 一部として提供される Web サービスの詳細については、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]を参照してください[BizTalk ESB Toolkit の Web サービスを使用して](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)です。