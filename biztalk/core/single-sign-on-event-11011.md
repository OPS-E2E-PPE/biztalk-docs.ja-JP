---
title: シングル サインオン:イベント 11011 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4ef430a-fb3b-4bf7-936f-a866262a6c3a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35e22fca920554dccb36157a85419ee53993e255
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306537"
---
# <a name="single-sign-on-event-11011"></a>シングル サインオン:イベント 11011
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                               エンタープライズ シングル サインオン                                                                                                |
| 製品バージョン |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                         11011                                                                                                          |
|  イベント ソース   |                                                                                                         ENTSSO                                                                                                         |
|    コンポーネント    |                                                                                                          なし                                                                                                           |
|  シンボル名  |                                                                                                 SSO_WARN_NOT_APP_ADMIN                                                                                                 |
|  メッセージ テキスト   | クライアント ユーザーはアプリケーション管理者 account.%r のメンバーではありません。<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> アプリケーション名: % 4 %r<br /><br /> アプリケーション管理者: %5 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは、アプリケーション管理者アカウントのメンバーではないです。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 状況を解決するには、アプリケーションの管理者アカウントのメンバー、クライアント ユーザーを作成する必要があります。 この警告を今後表示しないを停止するには、監査レベルを下げることです。