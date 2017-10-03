---
title: "BAM プライマリ インポート データベース参照を無効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6efa79822f6a5406db29c69b5ba0892a63bcc5f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a>BAM プライマリ インポート データベースへの参照を無効にする方法 
管理者を使用して、**無効参照**指定された BAM プライマリ インポート データベースへの参照を無効にするコマンド。  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を無効にするには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm 無効参照 TargetServer:\<対象サーバー > - TargetDatabase:\<対象データベース > [-サーバー:\<サーバー >] [-データベース:\<データベース >]**ここで、  **\<** *ターゲット サーバー*  **>** 先の SQL サーバーの名前に置き換え指定されたターゲットの BAM プライマリ インポート データベース\<*ターゲット データベース*> が存在します。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)