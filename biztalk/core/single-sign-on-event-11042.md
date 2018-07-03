---
title: 'シングル サインオン: イベント 11042 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1927bb5-a400-4e3a-8f80-95ef5693216c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 109678e68c3624cec11c4c9f235063288f342f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985691"
---
# <a name="single-sign-on-event-11042"></a>シングル サインオン: イベント 11042
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                   |
| 製品バージョン |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    イベント ID     |                                                                                                                                                             11042                                                                                                                                                             |
|  イベント ソース   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                              なし                                                                                                                                                              |
|  シンボル名  |                                                                                                                                                SSO_WARN_ACCESS_DENIED_ACCOUNTS                                                                                                                                                |
|  メッセージ テキスト   | アクセスが拒否されました。<br /><br /> この機能を実行するには、クライアント ユーザーは次のいずれかのアカウントのメンバーである必要があります。%r<br /><br /> SSO 管理者: % 1 %r<br /><br /> SSO 関連管理者: % 2 %r<br /><br /> アプリケーション管理者: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> 追加データ: %5 |
  
## <a name="explanation"></a>説明  
 この機能を実行するには、クライアント ユーザーは警告で示されているいずれかのアカウントのメンバーである必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この機能を実行するには、いずれかのアカウントに加わる必要があります。