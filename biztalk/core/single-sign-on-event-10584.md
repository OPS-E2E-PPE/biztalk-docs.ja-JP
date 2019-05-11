---
title: シングル サインオン:イベント 10584 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9377d-b4fd-48a6-961a-3629b3db644a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 478d33b1ef00930617a32f18dc7cf942210e0162
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395252"
---
# <a name="single-sign-on-event-10584"></a>シングル サインオン:イベント 10584
## <a name="details"></a>詳細  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                    |
| 製品バージョン |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10584                              |
|  イベント ソース   |                             ENTSSO                             |
|    コンポーネント    |                              なし                               |
|  シンボル名  |                   SSO_WARN_NO_IMPERSONATION                    |
|  メッセージ テキスト   | Client.%r を偽装できませんでした。<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 クライアントの偽装は、ENTSSO システムでは、クライアントの身元を確認します。 システムは、クライアントを偽装することは、次の 3 つのいずれかが発生した可能性があります。 クライアントが通常のアクティビティを実行しよう、クライアントがシステムのセキュリティに侵入しようまたはクライアント アプリケーションが偽装をブロックする設計されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 クライアント アプリケーションを見つけて、試行を行うには、権限借用でブロックされるかどうかを判断します。