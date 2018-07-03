---
title: BAM インフラストラクチャの変更を一覧表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definitions [BAM], listing infrastructure changes
- managing [BAM definitions], listing infrastructure changes
- Get-Changes command [BAM]
- infrastructure, listing changes [BAM]
ms.assetid: 3feacd7d-6f42-4626-835b-0dc3befc9fd6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4c0d2efc67e4329502b0eac7a11ddbd72f8bcee
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998083"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a>BAM インフラストラクチャへの変更を一覧表示する方法
管理者を使用して、 **get 変更**展開された BAM 定義に関する現在の情報を一覧に、BAM 管理ユーティリティのコマンド。 このコマンドでは、BAM プライマリ インポート データベースの現在の展開アイテムを一覧表示することもできます。  
  
 表示される情報には、成功した展開と展開解除、BAM 定義ファイルの名前、BAM 構成ファイルの名前、定義ファイルに関連付けられたすべてのアクティビティとビューの名前、および変更を適用したユーザー アカウントが含まれます。 get-changes の一覧には、展開した定義と削除した定義が、それに関連付けられた識別番号と共に表示されます。  
  
### <a name="to-list-changes-to-the-bam-definition"></a>BAM 定義への変更を一覧表示するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3. 型**bm get に変更します。**  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)