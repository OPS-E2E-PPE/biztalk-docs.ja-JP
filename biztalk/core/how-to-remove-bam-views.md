---
title: "BAM ビューを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, views
- managing [BAM definitions], deleting views
- Remove-View command [BAM]
ms.assetid: 1a43ec81-20b1-41f7-941f-753132ac9ed2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d8930fb4e3f2014945b743b15da4dbdfff3451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-bam-views"></a>BAM ビューを削除する方法
管理者を使用して、**削除ビュー** BAM プライマリ インポート データベースからビューを削除するコマンド。  
  
> [!NOTE]
>  ビューを削除すると、そのビューに定義された警告も自動的に削除されます。  
  
### <a name="to-remove-bam-views"></a>BAM ビューを削除するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  」と入力して、追跡フォルダーに移動**C:\Program files \microsoft BizTalk Server 2009 \tracking**コマンド プロンプトでします。 **Enter**キーを押します。  
  
3.  型**bm 削除ビューの名前:\<ビュー名 >**です。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [BAM 警告を削除する方法](../core/how-to-remove-bam-alerts.md)