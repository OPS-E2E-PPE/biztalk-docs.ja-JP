---
title: アイテムの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], artifacts
- managing [artifacts]
- artifacts, managing
- managing [artifacts], about managing artificats
ms.assetid: aa7c5e60-7c16-4bcf-b913-b1bdfc5c7543
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2327f1093658a7d6e01472e393fea40120abd6c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380402"
---
# <a name="managing-artifacts"></a>アイテムの管理
このセクションは、アーティファクトを管理する方法を説明を追加し、BizTalk アプリケーションから削除する方法など、そのプロパティを構成する方法。  
  
 成果物は、その実行に必要な BizTalk アプリケーションに含まれる項目です。 BizTalk アプリケーションでの成果物の使用方法については、次を参照してください[BizTalk アプリケーションとは何ですか?。](../core/what-is-a-biztalk-application.md) アイテムの背景については、次を参照してください。[ランタイム アーキテクチャ](../core/runtime-architecture.md)します。 作成して BizTalk アプリケーションを変更するときにアイテムを操作する方法については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。  

## <a name="tracking-artifacts"></a>成果物を追跡
作成するアイテムの管理の大きな部分を追跡します。 オーケストレーションの実行時にさまざまな追跡オプションを構成、送信ポート、受信ポート、およびパイプラインが BizTalk Server 管理コンソールを使用することができます。 項目の追跡オプションは、ビジネス プロセスを中断することがなく、いつでも変更できます。

追跡構成設定では、次の種類のデータを追跡することができます。

- 受信または送信イベント データ。 たとえば、メッセージ ID、開始、停止、成果物の時間します。

- 受信または送信メッセージのプロパティです。 たとえば、アイテムが処理される各メッセージの [全般] と昇格させたプロパティです。

- 受信または送信メッセージの本文および部分。 たとえば、本文とメッセージごとにアイテムが処理する部分。

- オーケストレーションします。 オーケストレーション図形のデータを実行します。

[追跡メッセージおよびインスタンス データを表示する](../core/viewing-tracked-message-and-instance-data.md)なかなかよい情報を提供します。 


> [!TIP]
> パイプラインに追跡オプションを設定した場合、追跡オプションはグローバルに設定パイプラインを使用するすべてのポートに対して。 これは、結果より多くのデータの場合があり、システムのパフォーマンスに影響を与える可能性よりも追跡されています。 開発中は、通常この可能性があります。 運用環境シナリオでは、送信ポートの追跡オプションを有効にし、受信ポートのパイプラインではなく、お勧めします。
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [オーケストレーションの管理](../core/managing-orchestrations.md)  
  
-   [ロール リンクの管理](../core/managing-role-links.md)  
  
-   [送信ポートと送信ポート グループの管理](../core/managing-send-ports-and-send-port-groups.md)  
  
-   [受信ポートの管理](../core/managing-receive-ports.md)  
  
-   [受信場所の管理](../core/managing-receive-locations.md)  
  
-   [ポリシーの管理](../core/managing-policies.md)  
  
-   [スキーマの管理](../core/managing-schemas.md)  
  
-   [マップの管理](../core/managing-maps.md)  
  
-   [パイプラインの管理](../core/managing-pipelines.md)  
  
-   [リソースの管理](../core/managing-resources.md)