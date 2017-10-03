---
title: "シングル サインオン: イベント 11052 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c797ed19-7613-4e0f-8867-9258ec3776a4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa45afc85535cd0107d43e795b6e3f97fcc5f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11052"></a>シングル サインオン: イベント 11052
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11052|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_SSO_AFF_ADMIN_NOT_GROUP|  
|メッセージ テキスト|SSO 関連管理者アカウントに、1 つ以上の単独 (グループではない) アカウントが含まれています。 これらの単独アカウントが Active Directory またはローカル コンピューターから削除された場合は、そのアカウントを直ちに SSO システムから削除する必要があります。削除しない場合、セキュリティ リスクになるおそれがあります。%r<br /><br /> SSO 関連管理者: %1 %r<br /><br /> 個々 のアカウント: %2|  
  
## <a name="explanation"></a>説明  
 単独アカウントを Active Directory またはローカル コンピューターから削除しても、SSO システムからそのアカウントが自動的に削除されるわけではありません。 つまり、アカウント USER1 がローカルで削除され、その後、別のユーザー (新入社員など) が同じ名前でシステムに参加した場合、元の USER1 が持っていたすべてのセキュリティ権限が SSO システムによって新しい USER1 に付与されることになります。 これにより、セキュリティ上のリスクが発生します。  
  
 SSO 管理者アカウントでは Active Directory グループ (単独ではない) アカウントを使用することをお勧めします。  
  
## <a name="user-action"></a>ユーザーの操作  
 単独アカウントが Active Directory またはローカル コンピューターから削除されるまで、何もする必要はありません。 単独アカウントが削除された時点で、そのアカウントをできるだけ早く SSO システムから削除する必要があります。