---
title: サイド バイ サイド バージョン管理を使用して更新しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9721a091-98ec-4f0b-ad1f-6ca184956e7c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36be63c9cef6a016ea4ad34d98a2750be86491d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974259"
---
# <a name="updating-using-side-by-side-versioning"></a>サイド バイ サイド バージョン管理を使用して更新しています
ダウンタイム、スケジュールを設定または終了することはできません非常に長時間のオーケストレーション インスタンスがある場合は、サイド バイ サイド バージョン管理が必要な場合があります。 この種類のアップグレードでは、同じアプリケーションまたはアプリケーションの成果物の 2 つのバージョンは、サイド バイ サイドでを実行します。 .NET ランタイムで本質的に展開する同じ名前しますが、異なるバージョンのアセンブリと実行、および BizTalk Server もできます。  
  
 アプリケーションのバージョンをサイド バイ サイドでは、たとえば利用できるようにするビジネス パートナーのサブセットにすべてのパートナーではなく、最初に 1 回、主要なアプリケーションのアップグレードのロールアウトを段階的にする場合に便利です。 この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。  
  
 アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。 代わりに、元のアプリケーションから別の名前を持つ新しいアプリケーションを作成し、アプリケーションのアイテムの新しいバージョンを設定します。  
  
 アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。  
  
 ステップ バイ ステップのアプリケーションまたはサイド バイ サイド バージョン管理を使用してオーケストレーションを更新するために必要なタスクの一覧を表示するには、次を参照してください[チェックリスト: サイド バイ サイドで、アプリケーションを使用してバージョン管理を更新](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)と[チェックリスト: 更新します。サイド バイ サイド バージョン管理を使用してオーケストレーション](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)します。 アプリケーションのサイド バイ サイドで配置する方法の詳細については、次を参照してください。"[既存のバージョンで実行して並列アプリケーションの新しいバージョンをデプロイする方法](http://go.microsoft.com/fwlink/?LinkId=155143)(<http://go.microsoft.com/fwlink/?LinkId=155143>) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サイドバイサイドのバージョン管理を使用したマップの更新方法](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [サイドバイサイドのバージョン管理を使用したパイプラインの更新方法](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [サイドバイサイドのバージョン管理を使用したスキーマの更新](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)