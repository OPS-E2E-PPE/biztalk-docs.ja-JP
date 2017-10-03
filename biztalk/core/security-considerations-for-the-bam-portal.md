---
title: "BAM ポータルのセキュリティに関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b0f5220eba5b66daf41dffc7ab74f93df8bb509
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="security-considerations-for-the-bam-portal"></a>BAM ポータルのセキュリティに関する考慮事項
最小特権の原則に従って、ユーザー アカウントには、BAM ポータルでは定型的なタスクのみを実行できる、制限付きのアクセス許可を与える必要があります。 セキュリティと適切なユーザー アクセスとのバランスが取れるように BAM のユーザー アカウントを設定する際は、次のことに注意してください。  
  
## <a name="user-accounts"></a>ユーザー アカウント  
 最低限の権限を持つユーザー アカウントは、BAM ポータル分散 navigationfeature を使用することはできません。 この機能を使用できるようにするには、ローカル コンピューターだけでなくリモート コンピューターの Web サービスにもアクセスできるように十分なアクセス許可を与える必要があります。  
  
 BAM Web サービスのユーザー アカウントは、すべての参照データベースにアクセスするのに十分なアクセス許可を持っていて、参照データベースの BAM_ManagementWS ロールのメンバーであることが必要です。  
  
 特定のユーザーの種類に関する考慮事項を次に示します。  
  
-   ドメイン ユーザーは、アクセス対象のプライマリ インポート データベースをホストしているリモート コンピューターに対するアクセス許可を持っている必要があります。  
  
-   ローカル ユーザー ロールを割り当てられているユーザーは、分散ナビゲーションを使用できません。  
  
## <a name="administrator-accounts"></a>管理者アカウント  
 ドメイン ユーザーにアクセス許可を与えるには、管理者が securityadmin または sysadmin グループのメンバーである必要があります。  
  
 BAM 管理ユーティリティを実行するには、少なくとも BAM データベースのデータベース オペレーターである必要があります。  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)