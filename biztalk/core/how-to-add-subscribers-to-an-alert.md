---
title: "警告にサブスクライバーを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e86bde9f47e04c17f62c3cacff5d779cf0bed56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-subscribers-to-an-alert"></a>サブスクライバーを警告に追加する方法
管理者を使用して、**サブスクリプションの追加**コマンドを指定した警告にサブスクライバーを追加します。  
  
### <a name="to-add-subscribers-to-an-alert"></a>サブスクライバーを警告に追加するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3.  「`bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.  
  
    > [!NOTE]
    >  *型*BAM を使用して、アラートを配信する配信方法を指定します。 配信方法として電子メールを指定した場合は、警告の配信先となる電子メール アドレスを指定する必要があります。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [サブスクライバーを警告から削除する方法](../core/how-to-remove-subscribers-from-an-alert.md)