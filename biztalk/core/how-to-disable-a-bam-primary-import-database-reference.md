---
title: BAM プライマリ インポート データベース参照を無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d2d644-6ebb-4051-ae59-af7d0fb75753
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc9afef7bdcfad84f105abda158c5ed5c6461619
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968896"
---
# <a name="how-to-disable-a-bam-primary-import-database-reference"></a>BAM プライマリ インポート データベースへの参照を無効にする方法 
管理者を使用して、**無効参照**指定された BAM プライマリ インポート データベースへの参照を無効にするコマンド。  
  
### <a name="to-disable-a-reference-to-a-bam-primary-import-database"></a>BAM プライマリ インポート データベースへの参照を無効にするには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm 無効参照 TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>[-サーバー:\<サーバー\> ][-データベース:\<データベース\>]** ここで、  **\<** *ターゲット サーバー*  **\>** で指定されたターゲットの BAM プライマリ インポート データベース、SQL server の名前は置き換え\<*ターゲット データベース*\>が存在します。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)