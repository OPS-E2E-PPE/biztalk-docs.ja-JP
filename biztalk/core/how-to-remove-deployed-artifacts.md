---
title: 展開済みのアイテムを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM definitions], undeploying artifacts
- Remove-All command
- undeploying, artifacts [BAM]
- artifacts, undeploying [BAM]
ms.assetid: 90135965-d18e-4a71-9877-d2b0c3caf59f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cea6c9e72b9820420888551e8d36f3aaac3762b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384299"
---
# <a name="how-to-remove-deployed-artifacts"></a>展開済みのアイテムを削除する方法
管理者を使用して、**すべて削除**BAM プライマリ インポート データベースに展開されたアイテムを削除するコマンド。 指定する BAM 定義は、XML ファイルまたは削除するアイテムについての Excel ブックのコンテナー情報のいずれかです。  
  
### <a name="to-remove-deployed-artifacts"></a>展開済みのアイテムを削除するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. 型**bm のすべての削除に-definitionfile:\<def ファイル\>** します。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [アプリケーションに BAM アイテムを追加する方法](../core/how-to-add-a-bam-artifact-to-an-application.md)   
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM のセキュリティに関する推奨事項](../core/bam-security-recommendations.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)