---
title: シングル サインオン:イベント 11042 |Microsoft Docs
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
ms.openlocfilehash: bef9cdffc7e1b11409491ad27bb195d40c639518
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400981"
---
# <a name="single-sign-on-event-11042"></a>シングル サインオン:イベント 11042
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                                   エンタープライズ シングル サインオン                                                                                                                                                   |
| 製品バージョン |                                                                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                   |
|    イベント ID     |                                                                                                                                                             11042                                                                                                                                                             |
|  イベント ソース   |                                                                                                                                                            ENTSSO                                                                                                                                                             |
|    コンポーネント    |                                                                                                                                                              なし                                                                                                                                                              |
|  シンボル名  |                                                                                                                                                SSO_WARN_ACCESS_DENIED_ACCOUNTS                                                                                                                                                |
|  メッセージ テキスト   | アクセスが拒否されました。<br /><br /> クライアント ユーザーはこの function.%r を実行するには、次のアカウントのいずれかのメンバーである必要があります。<br /><br /> SSO 管理者: % 1 %r<br /><br /> SSO 関連管理者: % 2 %r<br /><br /> アプリケーション管理者: % 3 %r<br /><br /> アプリケーション ユーザー: % 4 %r<br /><br /> 追加データ: %5 |
  
## <a name="explanation"></a>説明  
 クライアント ユーザーは、この機能を実行する警告の一覧にあるアカウントのいずれかのメンバーである必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この機能を実行するアカウントのいずれかに参加する必要があります。