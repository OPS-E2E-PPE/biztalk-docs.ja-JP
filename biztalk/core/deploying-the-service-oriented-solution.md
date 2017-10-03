---
title: "指向ソリューションのサービスの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7246635c4e0d55fd424fd0052eee91e118c8cb17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-the-service-oriented-solution"></a>指向ソリューションのサービスの展開
サービス指向のアーキテクチャ (SOA) は、分散システムを構築するためのアプローチです。 サービス指向ソリューションでは、クライアントで使用できる 1 つのサービスにさまざまなプロトコルを使用して複数のバックエンド システムを集計することができますを示しています。 このソリューションでは、配信およびパフォーマンスの特性を保証するアプローチで各種のサービスを統合しています。  
  
 サービス指向ソリューションは、サービス レベル契約のシナリオをモデル化しています。ソリューションに接続されている BizTalk Server および基幹業務 (LOB) アプリケーション サーバーは、3 秒以内にサービス要求に応答する必要があります。 この 3 秒間のうちの 1 秒は、BizTalk Server によって消費される場合があります。  
  
 このセクションの各トピックでは、サービス指向ソリューションを 1 台のコンピュータおよび複数の実稼働サーバーにインストールし、テストする方法について説明します。  
  
> [!NOTE]
>  サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。 サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)です。  
  
 **対象読者**  
  
 このドキュメントは、BizTalk Server、Windows Server、および Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に関する知識があることを前提としています。 また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。 さらに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを作成する方法や、プロジェクトの作成、参照の設定、デバッグ モードを使用したソリューションのデバッグおよびテストに関しても理解しておいてください。 IT 担当者および開発者の必要なスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [開発者のコンピュータ設定、サービス指向ソリューション](../core/developer-machine-setup-for-the-service-oriented-solution.md)