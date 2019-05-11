---
title: シングル サインオン:イベント 11051 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fe767818-f74e-415c-9287-5b7cc46e358a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4375b2a018fa649ef795e425e83078ac3add5cef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400919"
---
# <a name="single-sign-on-event-11051"></a>シングル サインオン:イベント 11051
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                          エンタープライズ シングル サインオン                                                                                                                                                           |
| 製品バージョン |                                                                                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                          |
|    イベント ID     |                                                                                                                                                                    11051                                                                                                                                                                     |
|  イベント ソース   |                                                                                                                                                                    ENTSSO                                                                                                                                                                    |
|    コンポーネント    |                                                                                                                                                                     なし                                                                                                                                                                      |
|  シンボル名  |                                                                                                                                                         SSO_WARN_SSO_ADMIN_NOT_GROUP                                                                                                                                                         |
|  メッセージ テキスト   | SSO 管理者アカウントには、1 つまたは複数の個人が含まれています (グループではない) アカウント。 この単独アカウントが Active Directory またはローカル コンピューターから削除された場合は、SSO システムからすぐに削除する必要があります。 またはセキュリティ risk.%r になる可能性があります。<br /><br /> SSO 管理者: % 1 %r<br /><br /> 個々 のアカウント: %2 |
  
## <a name="explanation"></a>説明  
 Active Directory またはローカル コンピューターから個別のアカウントを削除する自動的にアカウントは削除されず、SSO システムから。 つまり、アカウントの USER1 がローカルで削除し、別のユーザー (たとえば、新しい従業員) に同じ名前を使用して、システムが参加している場合、SSO システムは新しい USER1 に付与、元の USER1 が所有するすべてのセキュリティ権限。 ここで、セキュリティ リスクが生じる。  
  
## <a name="user-action"></a>ユーザーの操作  
 操作は必要ありません、個々 のアカウントが Active Directory またはローカル コンピューターから削除されるまでです。 その時点では、SSO システムから個々 のアカウントをできるだけ早く削除する必要があります。