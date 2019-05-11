---
title: シングル サインオン:イベント 11009 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5f06f8c-1614-4538-83e6-689657135776
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d53f665ae1f900506d1bfc71873a1c40311faea0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306627"
---
# <a name="single-sign-on-event-11009"></a>シングル サインオン:イベント 11009
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                     |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                      エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                      |
|    イベント ID     |                                                                                11009                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                                |
|    コンポーネント    |                                                                                 なし                                                                                 |
|  シンボル名  |                                                                       SSO_WARN_NOT_SSO_ADMIN                                                                        |
|  メッセージ テキスト   | クライアント ユーザーは SSO 管理者 account.%r のメンバーではありません。<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> SSO 管理者: %4 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは SSO 管理者アカウントのメンバーではないです。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 状況を解決するには、クライアントのユーザーに SSO 管理者アカウントのメンバーを作成する必要があります。 この警告を今後表示しないを停止するには、監査レベルを下げることです。