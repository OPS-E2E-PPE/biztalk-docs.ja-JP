---
title: "BAM ポータル ページのレイアウト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal
- Portal page [BAM portal]
ms.assetid: 0d8833b7-dd2f-475c-a890-e925ee47d219
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5569021698eb856d7584a2510a27d69f092f37a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="bam-portal-page-layout"></a>BAM ポータル ページのレイアウト
BAM ポータル ページは、次の 3 つのフレームにレイアウトされます。  
  
-   バナー  
  
-   マイ ビュー  
  
-   コンテンツ  
  
## <a name="banner"></a>バナー  
 **バナー**フレームはポータル ページの上部に配置します。 バナー フレームには、会社名、ロゴ、そのページのユーザー インターフェイス (UI)、およびページ タイトルのヘルプへのリンクなどのブランド化の情報が含まれています。 企業に関する情報は、必要に応じてカスタマイズできます。 バナーのブランド情報をカスタマイズする方法の詳細については、次を参照してください。 [BAM ポータルの構成をカスタマイズする](../core/customizing-the-bam-portal-configuration.md)です。  
  
## <a name="my-views"></a>マイ ビュー  
 **マイ ビュー**フレームはポータル ページの左側にあります。 マイ ビューには、ユーザーがアクセス許可を与えられているすべてのビューが表示されます。 それぞれのビューで使用できる機能を確認するには、各ビューを展開します。 ビューが表示されない場合は、ビューが作成されていないか、ユーザーにアクセス許可が与えられていないかのどちらかです。ビューの作成は通常、ビジネス アナリストが実行するタスクで、権限の許可は通常、管理者が実行するタスクです。  
  
 各ビューのビュー内では、次の 3 つのタスクを実行できます。  
  
-   **アクティビティの検索**: クエリと、アクティビティに基づいて警告を作成することができます。  
  
-   **集計**: 集計データを表示して、ピボット テーブル グラフの合計に基づいて警告を作成できます。  
  
-   **警告マネージャー**: 編集、表示、およびアラートに配信登録を作成することができます。  
  
> [!NOTE]
>  マイ ビュー フレームから警告マネージャーを選択した場合、既存の警告の編集のみを行うことができます。 新しい警告を作成するには、アクティビティの検索ページまたは集計ページから警告マネージャー ページに移動する必要があります。  
  
## <a name="content"></a>コンテンツ  
 **コンテンツ**フレームはポータル ページの右側にあります。 コンテンツ ページには、マイ ビューの各タスク (アクティビティの検索、集計、および警告管理) によって提供された情報が表示されます。 タスクを選択すると、そのタスクに関連する機能を反映してコンテンツ フレームが変化します。  
  
## <a name="see-also"></a>参照  
 [BAM ポータルにアクティビティの検索 ページ](../core/activity-search-on-the-bam-portal-page.md)   
 [BAM ポータルの集計 ページ](../core/aggregations-on-the-bam-portal-page.md)   
 [警告マネージャーで、BAM ポータル ページ](../core/alert-manager-on-the-bam-portal-page.md)   
 [BAM ポータル](../core/bam-portal.md)