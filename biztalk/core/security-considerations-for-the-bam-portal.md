---
title: BAM ポータルのセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, administrator accounts
- user accounts, BAM
- administrator accounts, BAM portal
- BAM portal, user accounts
- security, BAM portal
ms.assetid: 5c8e6034-dfb8-4dba-b040-0c19504abdb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22aa95167640482ccd2e00dfbfd98b0a323da1a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280316"
---
# <a name="security-considerations-for-the-bam-portal"></a>BAM ポータルのセキュリティに関する考慮事項
最小特権の原則を使用して、ユーザー アカウントは、BAM ポータルでの日常的なタスクを実行する制限の厳しいアクセス許可が必要です。 ユーザーの適切なアクセス権を持つセキュリティのバランスを取るように BAM のユーザー アカウントを設定する際に注意してください、次の点を保持します。  
  
## <a name="user-accounts"></a>ユーザー アカウント  
 最小限のアクセス許可を持つユーザー アカウントを使用して、BAM ポータル分散 navigationfeature されません。 この機能を使用できるようにするには、これらのアカウントは、ローカル コンピューターとリモート コンピューターでは、Web サービスへのアクセスを許可するための十分なアクセス許可が必要です。  
  
 BAM Web サービスのユーザー アカウントは、すべての参照先データベースにアクセスする権限が必要し、参照先のデータベースの BAM_ManagementWS ロールのメンバーである必要があります。  
  
 次のユーザーの種類のこれらの考慮事項の注意する必要があります。  
  
-   ドメイン ユーザー、アクセス許可が必要リモート コンピューター上でそのプライマリ インポート データベースをホストにアクセスします。  
  
-   ローカル ユーザーのロールが割り当てられたユーザーは、分散ナビゲーションを使用できません。  
  
## <a name="administrator-accounts"></a>管理者アカウント  
 管理者は、ドメイン ユーザーに権限を与える securityadmin または sysadmin グループのメンバーである必要があります。  
  
 BAM 管理ユーティリティを実行するには、BAM データベースの場合は、少なくともデータベース オペレーターがあります。  
  
## <a name="see-also"></a>参照  
 [BAM ポータル](../core/bam-portal.md)