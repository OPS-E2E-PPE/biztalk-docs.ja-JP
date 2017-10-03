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
ms.openlocfilehash: ee5958120e364cc0c2661ead6100bd2ba5502226
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-bam-configuration-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成を更新する方法
管理者は、BAM 管理ユーティリティを使用して、既存の BAM を更新できます。  
  
## <a name="prerequisites"></a>前提条件  
 更新された BAM データベースに対する管理者権限が必要です。  
  
### <a name="to-update-the-bam-configuration-using-the-bam-management-utility"></a>BAM 管理ユーティリティを使用して BAM 構成を更新するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  コマンド ライン プロンプトで、次を入力: **bm 更新 config ファイル名:\<構成ファイル >**ここで、 \<*構成ファイル*> は、BAM の名前に置換構成ファイルです。 **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)