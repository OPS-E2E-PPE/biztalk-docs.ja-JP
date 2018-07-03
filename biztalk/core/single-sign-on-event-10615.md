---
title: 'シングル サインオン: イベント 10615 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5dd0041-2dfd-4fd1-97ec-f9fc719a6fcc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86b99f901ba60749386d055ce771beed225e4a18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008467"
---
# <a name="single-sign-on-event-10615"></a>シングル サインオン: イベント 10615
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                エンタープライズ シングル サインオン                                                                                                                |
| 製品バージョン |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    イベント ID     |                                                                                                                          10615                                                                                                                          |
|  イベント ソース   |                                                                                                                         ENTSSO                                                                                                                          |
|    コンポーネント    |                                                                                                                           なし                                                                                                                           |
|  シンボル名  |                                                                                                            SSO_WARN_NO_UPDATE_TICKET_TIMEOUT                                                                                                            |
|  メッセージ テキスト   | アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。%r<br /><br /> クライアント ユーザー: 1 %r<br /><br /> SSO 管理者: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 アプリケーションのチケット タイムアウトを変更するには、クライアント ユーザーは SSO 管理者アカウントのメンバーであることが必要です。  
  
## <a name="user-action"></a>ユーザーの操作  
 システム管理者に連絡し、SSO 管理者アカウントのメンバーを探して、この変更を行います。