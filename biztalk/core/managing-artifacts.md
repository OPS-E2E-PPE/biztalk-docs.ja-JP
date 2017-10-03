---
title: "成果物の管理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ccca48682f009a24f538015b055c45dd79a9587
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-artifacts"></a>アイテムの管理
このセクションでは、アイテムの管理方法について説明します。BizTalk アプリケーションにアイテムを追加したり、BizTalk アプリケーションからアイテムを削除したりする方法のほか、アイテムのプロパティを構成する方法などを紹介します。  
  
 BizTalk アプリケーションには、その実行に必要なアイテムが含まれています。 BizTalk アプリケーション内の成果物の使用方法に関する背景情報については、次を参照してください。 [BizTalk アプリケーションは何ですか。](../core/what-is-a-biztalk-application.md) バック グラウンド成果物については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)です。 作成および BizTalk アプリケーションを変更するときにアイテムを操作する方法については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)です。  

## <a name="tracking-artifacts"></a>成果物を追跡
大きな部分を作成するアイテムを管理するを追跡します。 BizTalk Server 管理コンソールを使用して、オーケストレーション、送信ポート、受信ポート、およびパイプラインの実行時にさまざまな追跡オプションを構成できます。 項目の追跡オプションは、ビジネス プロセスを中断することなく、いつでも変更できます。

追跡の構成設定では、次の種類のデータを追跡することができます。

- 受信または送信イベント データ。 たとえば、メッセージ ID、アイテムの開始時刻および停止時刻です。

- 受信または送信メッセージ プロパティ。 たとえば、アイテムが処理する各メッセージの全般プロパティや昇格させたプロパティです。

- 受信または送信メッセージの本文および部分。 たとえば、アイテムが処理する各メッセージの本文やその他の部分です。

- オーケストレーションです。 オーケストレーション図形の実行データ。

[追跡メッセージおよびインスタンス データを表示する](../core/viewing-tracked-message-and-instance-data.md)よい情報を提供します。 


> [!TIP]
> パイプラインに追跡オプションを設定した場合、追跡オプションはに対してグローバルに設定、パイプラインを使用するすべてのポートです。 これは、結果より多くのデータの追跡を超える場合があり、システムのパフォーマンスに影響を与える可能性があります。 開発中は、通常この可能性があります。 実稼働のシナリオで、送信ポートの追跡オプションを有効にして、受信パイプラインではなく、ポートお勧めします。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションの管理](../core/managing-orchestrations.md)  
  
-   [ロール リンクの管理](../core/managing-role-links.md)  
  
-   [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [受信ポートの管理](../core/managing-receive-ports.md)  
  
-   [受信場所の管理](../core/managing-receive-locations.md)  
  
-   [ポリシーの管理](../core/managing-policies.md)  
  
-   [スキーマの管理](../core/managing-schemas.md)  
  
-   [マップを管理します。](../core/managing-maps.md)  
  
-   [パイプラインの管理](../core/managing-pipelines.md)  
  
-   [リソースの管理](../core/managing-resources.md)