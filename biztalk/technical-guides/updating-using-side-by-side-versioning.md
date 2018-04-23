---
title: サイド バイ サイドのバージョン管理を使用して更新 |Microsoft ドキュメント
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
ms.openlocfilehash: fe8264b76867c2f4fa3200f906e1d99975c9e0eb
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="updating-using-side-by-side-versioning"></a>サイド バイ サイドのバージョン管理を使用して更新
できない場合は、ダウンタイムをスケジュールまたは終了できません非常に長時間のオーケストレーション インスタンスがある、サイド バイ サイドのバージョン管理が必要な場合があります。 この種類のアップグレードでは、同じアプリケーションまたはアプリケーションのアイテムの 2 つのバージョンは、サイド バイ サイドを実行します。 .NET ランタイム本質的には、同じ名前が、異なるバージョンのアセンブリを展開して実行、および BizTalk Server もできます。  
  
 アプリケーションのサイド バイ サイドのバージョン管理は、たとえばが使用できるようにビジネス パートナーのサブセットにすべてのパートナーではなく、最初に、1 回にアプリケーションの大幅アップグレードを段階的ロールアウトする場合に便利です。 この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。  
  
 アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。 代わりに、元のアプリケーションから別の名前を持つ新しいアプリケーションを作成し、アプリケーションのアイテムの新しいバージョンで作成します。  
  
 アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。  
  
 ステップ バイ ステップのアプリケーションまたはサイド バイ サイドのバージョン管理を使用してオーケストレーションを更新するために必要なタスクの一覧を表示するには、次を参照してください[チェックリスト: サイド バイ サイド、アプリケーションを使用してバージョン管理の更新](../technical-guides/checklist-updating-an-application-using-side-by-side-versioning.md)と[チェックリスト: 更新します。サイド バイ サイドのバージョン管理を使用してオーケストレーション](../technical-guides/checklist-updating-an-orchestration-using-side-by-side-versioning.md)です。 アプリケーションのサイド バイ サイド展開方法の詳細については、次を参照してください。"[既存のバージョンで実行して並行アプリケーションの新しいバージョンを展開する方法](http://go.microsoft.com/fwlink/?LinkId=155143)(http://go.microsoft.com/fwlink/?LinkId=155143)で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [サイドバイサイドのバージョン管理を使用したマップの更新方法](../technical-guides/how-to-update-a-map-using-side-by-side-versioning.md)  
  
-   [サイドバイサイドのバージョン管理を使用したパイプラインの更新方法](../technical-guides/how-to-update-a-pipeline-using-side-by-side-versioning.md)  
  
-   [サイドバイサイドのバージョン管理を使用したスキーマの更新](../technical-guides/updating-a-schema-using-side-by-side-versioning.md)