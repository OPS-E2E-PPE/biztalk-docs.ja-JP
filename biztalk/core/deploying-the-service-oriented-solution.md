---
title: 指向ソリューションのサービスの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, service solution tutorial
- deploying, tutorials
- service solution tutorial, deploying
- service solution tutorial, background information
- tutorials, deploying
ms.assetid: 88d4d28d-9031-4fb8-ab62-04ee27949673
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d86b3b1cd1e5cadc8505e88db119cdffdaf653dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389544"
---
# <a name="deploying-the-service-oriented-solution"></a>指向ソリューションのサービスのデプロイ
サービス指向アーキテクチャ (SOA) は、分散システムを構築する方法です。 サービス指向ソリューションでは、クライアントが利用できる 1 つのサービスに集約できるさまざまなプロトコルを使用して複数のバックエンド システムを示します。 このソリューションでは、配信およびパフォーマンスの特性を保証するアプローチとサービスを統合します。  
  
 サービス指向ソリューションがモデルに BizTalk Server および基幹業務 (LOB) アプリケーション サーバーが接続されたサービス レベル アグリーメントによってシナリオには、サービス要求に応答する 3 秒が与えられます。 この 3 秒間のいずれかが占有されます、BizTalk Server でします。  
  
 このセクションのトピックでは、インストールして、1 台のコンピューターおよび複数の実稼働サーバー上のサービス指向ソリューションをテストする方法について説明します。  
  
> [!NOTE]
>  サービス指向ソリューションの 3 つのバージョンがあります。 アダプタ、インライン、およびスタブ。 サービス指向ソリューションの 3 つのバージョンの違いの詳細については、次を参照してください。[サービス指向ソリューションを理解する](../core/understanding-the-service-oriented-solution.md)します。  
  
 **対象読者**  
  
 このドキュメントは、BizTalk Server、Windows Server、および Microsoft に精通していることを前提としています。[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。 またを使用してアプリケーションをビルドする方法について理解しているが推奨[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]した参照の設定、デバッグおよびテスト ソリューションをデバッグ モードを使用してプロジェクトの作成について理解しているとします。 IT プロフェッショナルと開発者のスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サービス指向ソリューションに対する開発者のコンピューター設定](../core/developer-machine-setup-for-the-service-oriented-solution.md)