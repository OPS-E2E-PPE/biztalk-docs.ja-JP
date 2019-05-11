---
title: 警告にサブスクライバーを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- subscriptions, subscribers
- subscriptions
- managing [BAM], adding alert subscribers
ms.assetid: c76a117d-4516-4f48-995c-7e018dbba755
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034415c8252a8e8adde51136b11185803d39af40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387220"
---
# <a name="how-to-add-subscribers-to-an-alert"></a>警告にサブスクライバーを追加する方法
管理者を使用して、**サブスクリプションの追加**コマンドを指定した警告にサブスクライバーを追加します。  
  
### <a name="to-add-subscribers-to-an-alert"></a>警告にサブスクライバーを追加するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3. 「`bm add-subscription -View:<view name> -Alert:<alert name> -AccountName:<account name> -Type: [ File | Email ][ -Email:<e-mail address> ]`.  
  
   > [!NOTE]
   >  *型*BAM を使用して警告を配信する配信方法を指定します。 電子メールの配信の種類を指定する場合は、警告を配信する電子メール アドレスを指定する必要があります。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [サブスクライバーを警告から削除する方法](../core/how-to-remove-subscribers-from-an-alert.md)