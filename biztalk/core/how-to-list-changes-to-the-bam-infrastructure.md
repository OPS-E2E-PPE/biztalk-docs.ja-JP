---
title: "BAM インフラストラクチャに対する変更を一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d0ed240f156d853c18f28a52022eea585af513
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a>BAM インフラストラクチャへの変更を一覧表示する方法
管理者を使用して、 **get 変更**コマンドを BAM 管理ユーティリティの配置済みの BAM 定義に関する現在の情報を一覧表示します。 このコマンドでは、BAM プライマリ インポート データベースの現在の展開アイテムを一覧表示することもできます。  
  
 表示される情報には、成功した展開と展開解除、BAM 定義ファイルの名前、BAM 構成ファイルの名前、定義ファイルに関連付けられたすべてのアクティビティとビューの名前、および変更を適用したユーザー アカウントが含まれます。 get-changes の一覧には、展開した定義と削除した定義が、それに関連付けられた識別番号と共に表示されます。  
  
### <a name="to-list-changes-to-the-bam-definition"></a>BAM 定義への変更を一覧表示するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  型**bm get 変更します。**  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)