---
title: 追加の BAM プライマリ インポート データベースを参照する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea80b32c-f2cb-4aca-89f4-d5b72e1ba021
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fca916339e48f6bce053753111f4467a4c9ae7d5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969976"
---
# <a name="how-to-reference-additional-bam-primary-import-databases"></a>追加の BAM プライマリ インポート データベースを参照する方法
管理者を使用して、**参照を有効にする**コマンドを追加の BAM プライマリ インポート データベースを参照します。 分散 BAM アクティビティの表示を容易にするには、複数の BAM プライマリ インポート データベースを参照します。  
  
### <a name="to-enable-a-reference-to-an-additional-bam-primary-import-database"></a>追加の BAM プライマリ インポート データベースへの参照を有効にするには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm 参照を有効にする TargetServer:\<ターゲット サーバー\> - TargetDatabase:\<ターゲット データベース\>** ここで、 \<*ターゲット サーバー* \>で指定されたターゲットの BAM プライマリ インポート データベース、SQL server の名前は置き換え\<ターゲット データベース\>が存在します。 Enter キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)