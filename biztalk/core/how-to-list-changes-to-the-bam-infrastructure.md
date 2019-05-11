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
ms.openlocfilehash: 5bb796c7572e00c0a66cf89eb61035a46ac361c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336881"
---
# <a name="how-to-list-changes-to-the-bam-infrastructure"></a>BAM インフラストラクチャへの変更を一覧表示する方法
管理者を使用して、 **get 変更**展開された BAM 定義に関する現在の情報を一覧に、BAM 管理ユーティリティのコマンド。 BAM プライマリ インポート データベースの現在の展開アイテムを一覧表示するのに get-changes コマンドを使用することもできます。  
  
 情報には、成功した展開と展開解除、BAM 定義ファイルの名前、BAM 構成ファイルの名前、すべてのアクティビティと、定義ファイルと変更を適用したユーザー アカウントに関連付けられたビューの名前が含まれています。 Get 変更一覧には、展開と定義の削除とその関連付けられている識別番号が表示されます。  
  
### <a name="to-list-changes-to-the-bam-definition"></a>BAM 定義に変更を一覧表示  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. 型**bm get に変更します。**  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)