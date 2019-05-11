---
title: シングル サインオン:イベント 10615 |Microsoft Docs
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
ms.openlocfilehash: adece23afc79fcff2d4c0168aaee4b38819f5e50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397687"
---
# <a name="single-sign-on-event-10615"></a>シングル サインオン:イベント 10615
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                エンタープライズ シングル サインオン                                                                                                                |
| 製品バージョン |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    イベント ID     |                                                                                                                          10615                                                                                                                          |
|  イベント ソース   |                                                                                                                         ENTSSO                                                                                                                          |
|    コンポーネント    |                                                                                                                           なし                                                                                                                           |
|  シンボル名  |                                                                                                            SSO_WARN_NO_UPDATE_TICKET_TIMEOUT                                                                                                            |
|  メッセージ テキスト   | クライアント ユーザーは application.%r のチケット タイムアウトを変更するには、SSO 管理者アカウントのメンバーである必要があります。<br /><br /> クライアント ユーザー: 1 %r<br /><br /> SSO 管理者: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは、アプリケーションのチケット タイムアウトを変更するには、SSO 管理者アカウントのメンバーである必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この変更を行うには、SSO 管理者アカウントのメンバーの検索に役立つ、システム管理者に依頼します。