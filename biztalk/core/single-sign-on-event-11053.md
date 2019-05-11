---
title: シングル サインオン:イベント 11053 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 923ce671-6d52-44b2-ae77-7b16fcb50dac
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2249e618ecddbb1bfdabdbbdd34fe3baca71c99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400914"
---
# <a name="single-sign-on-event-11053"></a>シングル サインオン:イベント 11053
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                                                                                 |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                                                    エンタープライズ シングル サインオン                                                                                                                                                                                    |
| 製品バージョン |                                                                                                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                                                    |
|    イベント ID     |                                                                                                                                                                                              11053                                                                                                                                                                                              |
|  イベント ソース   |                                                                                                                                                                                             ENTSSO                                                                                                                                                                                              |
|    コンポーネント    |                                                                                                                                                                                               なし                                                                                                                                                                                               |
|  シンボル名  |                                                                                                                                                                                  SSO_WARN_APP_ADMIN_NOT_GROUP                                                                                                                                                                                   |
|  メッセージ テキスト   | アプリケーション管理者アカウントには、1 つまたは複数の個人が含まれています (グループではない) アカウント。 この単独アカウントが Active Directory またはローカル コンピューターから削除された場合は、SSO システムからすぐに削除する必要があります。 またはセキュリティ risk.%r になる可能性があります。<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション管理者: % 2 %r<br /><br /> 個々 のアカウント: %3 |
  
## <a name="explanation"></a>説明  
 Active Directory またはローカル コンピューターから個別のアカウントを削除する自動的にアカウントは削除されず、SSO システムから。 つまり、アカウントの USER1 がローカルで削除し、別のユーザー (たとえば、新しい従業員) に同じ名前を使用して、システムが参加している場合、SSO システムは新しい USER1 に付与、元の USER1 が所有するすべてのセキュリティ権限。 ここで、セキュリティ リスクが生じる。  
  
 ベスト プラクティスとしては、SSO 管理者アカウントが Active Directory グループ (単独ではない) アカウントを使用することをお勧めします。  
  
## <a name="user-action"></a>ユーザーの操作  
 操作は必要ありません、個々 のアカウントが Active Directory またはローカル コンピューターから削除されるまでです。 その時点では、SSO システムから個々 のアカウントをできるだけ早く削除する必要があります。