---
title: 'シングル サインオン: イベント 11071 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c0f61b9-cd86-482b-a8fe-0093a928c89b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74bc4793937574cc90021b95b6c1850409d57871
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975891"
---
# <a name="single-sign-on-event-11071"></a>シングル サインオン: イベント 11071
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                               |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                   エンタープライズ シングル サインオン                                                                                   |
| 製品バージョン |                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                   |
|    イベント ID     |                                                                                             11071                                                                                             |
|  イベント ソース   |                                                                                            ENTSSO                                                                                             |
|    コンポーネント    |                                                                                              なし                                                                                              |
|  シンボル名  |                                                                         SSO_WARN_PS_WIN_CHANGE_DISCARDED_ZERO_LENGTH                                                                          |
|  メッセージ テキスト   | Windows パスワードの長さが 0 文字であるため、Windows パスワード変更は破棄されました。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: % 2 %r<br /><br /> クライアント ユーザー: %3 |
  
## <a name="explanation"></a>説明  
 Windows パスワードの長さが 0 文字であるため、Windows パスワード変更は破棄されました。 Windows アカウントおよびクライアント ユーザー名は指定されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 SSO システムで要求される文字の数および種類に従って、もう一度パスワードを変更します。