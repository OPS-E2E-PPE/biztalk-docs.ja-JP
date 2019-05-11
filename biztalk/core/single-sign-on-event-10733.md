---
title: シングル サインオン:イベント 10733 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01520ae4-f692-4697-82ce-53a8a63b5bd9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3f67e18a9388e5f055d760d6223e2034ad6ea0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291794"
---
# <a name="single-sign-on-event-10733"></a>シングル サインオン:イベント 10733
## <a name="details"></a>詳細  

|                 |                                                                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                  エンタープライズ シングル サインオン                                                                  |
| 製品バージョン |                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                  |
|    イベント ID     |                                                                            10733                                                                            |
|  イベント ソース   |                                                                           ENTSSO                                                                            |
|    コンポーネント    |                                                                             該当なし                                                                             |
|  シンボル名  |                                                              SSO_WARN_PS_SET_WINDOWS_PASSWORD                                                               |
|  メッセージ テキスト   | SSO database.%r 内の Windows パスワードを更新できませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> Windows アカウント: %2\\% 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO データベース内の指定の Windows アカウントのパスワードを更新するパスワード同期が失敗したことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- 関連付けられているエラーのシステムおよびアプリケーション イベント ログを確認します。  

- 指定されたアカウントのパスワードが有効な Windows パスワードであることを確認します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
