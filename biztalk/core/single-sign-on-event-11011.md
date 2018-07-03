---
title: 'シングル サインオン: イベント 11011 |Microsoft Docs'
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
ms.openlocfilehash: 75ba98bf7fb3f57fdf9ce082028f2fff9ea7f618
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972971"
---
# <a name="single-sign-on-event-11011"></a>シングル サインオン: イベント 11011
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                               エンタープライズ シングル サインオン                                                                                                |
| 製品バージョン |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                         11011                                                                                                          |
|  イベント ソース   |                                                                                                         ENTSSO                                                                                                         |
|    コンポーネント    |                                                                                                          なし                                                                                                           |
|  シンボル名  |                                                                                                 SSO_WARN_NOT_APP_ADMIN                                                                                                 |
|  メッセージ テキスト   | クライアント ユーザーはアプリケーション管理者アカウントのメンバーではありません。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2\\% 3 %r<br /><br /> アプリケーション名: % 4 %r<br /><br /> アプリケーション管理者: %5 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーはアプリケーション管理者アカウントのメンバーではありません。 この警告は、監査レベルが高に設定されている場合にのみ表示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この状況に対処するには、クライアント ユーザーをアプリケーション管理者アカウントのメンバーにする必要があります。 今後警告を表示しない場合は、監査レベルを低くします。