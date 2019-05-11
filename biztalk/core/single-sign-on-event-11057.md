---
title: シングル サインオン:イベント 11057 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e165e24-fe43-4899-ab6e-1437f639f534
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff6e7a5c811c983ebe9f48fc6cdd85ed79f3ee16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400870"
---
# <a name="single-sign-on-event-11057"></a>シングル サインオン:イベント 11057
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                エンタープライズ シングル サインオン                                                                                                                |
| 製品バージョン |                                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                |
|    イベント ID     |                                                                                                                          11057                                                                                                                          |
|  イベント ソース   |                                                                                                                         ENTSSO                                                                                                                          |
|    コンポーネント    |                                                                                                                           なし                                                                                                                           |
|  シンボル名  |                                                                                                        SSO_WARN_PS_DIRECT_MISSING_INITIAL_CREDS                                                                                                         |
|  メッセージ テキスト   | 直接パスワード変更。 このマッピングのいくつか不足している外部資格情報フィールドを既定 values.%r に設定されています。<br /><br /> 追跡 ID: %1 %r<br /><br /> アプリケーション名: % 2 %r<br /><br /> Windows アカウント: % 3 %r<br /><br /> 外部アカウント: %4 |
  
## <a name="explanation"></a>説明  
 直接パスワード同期を使用してパスワードを変更することはできますが、この機能は 1 つの外部資格情報フィールドのみをサポートします。 ここで、ENTSSO システムは 1 つ以上の外部資格情報フィールドが発生しましたし、既定 (空白) 値にこれらのフィールドが設定します。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザー操作は必要ありません。