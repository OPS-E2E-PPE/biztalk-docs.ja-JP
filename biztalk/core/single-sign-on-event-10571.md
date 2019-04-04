---
title: 'シングル サインオン: イベント 10571 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c590a00-b8c5-41b4-abb3-0a424e8b052d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 638e04802b2d2cbf4b8089616ac29e451291b5d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009843"
---
# <a name="single-sign-on-event-10571"></a>シングル サインオン: イベント 10571
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                          エンタープライズ シングル サインオン                                                                                           |
| 製品バージョン |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                          |
|    イベント ID     |                                                                                                    10571                                                                                                     |
|  イベント ソース   |                                                                                                    ENTSSO                                                                                                    |
|    コンポーネント    |                                                                                                     なし                                                                                                      |
|  シンボル名  |                                                                                      SSO_WARN_SSO_NOT_IN_NEW_SSO_ADMIN                                                                                       |
|  メッセージ テキスト   | SSO 管理者アカウント名を変更するには、SSO サービス アカウントが新しい SSO 管理者アカウントのメンバーである必要があります。%r<br /><br /> SSO サービス アカウント: % 1 %r<br /><br /> 新しい SSO 管理者: %2 |
  
## <a name="explanation"></a>説明  
 SSO 管理者アカウント名を変更するには、SSO サービス アカウントが新しい SSO 管理者アカウントのメンバーである必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 ロールとアカウントの詳細については、[SSO ユーザー グループ](../core/sso-user-groups.md)を参照してください。