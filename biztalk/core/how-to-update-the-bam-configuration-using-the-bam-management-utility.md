---
title: "BAM 管理ユーティリティを使用して BAM 構成を更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 714a834e-1879-4019-9b54-e511705bd67a
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b08209d3b3a1555bbc674e469ea9f8a4b1f81a9d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成を更新する方法
管理者は、BAM 管理ユーティリティを使用して、既存の BAM を更新できます。  
  
## <a name="prerequisites"></a>前提条件  
 更新された BAM データベースに対する管理者権限が必要です。  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成を更新するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm 更新 config ファイル名:\<config ファイル\>**ここで、 \<*構成ファイル*\>はBAM 構成ファイルの名前に置換されます。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)