---
title: シングル サインオン:イベント 10585 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51c55ada-1ee3-4626-b044-9c537d11f0d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfca6095e57936df056558e84ec0ed8ecdb8b002
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530942"
---
# <a name="single-sign-on-event-10585"></a>シングル サインオン:イベント 10585
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                 エンタープライズ シングル サインオン                                                                                 |
| 製品バージョン |                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    イベント ID     |                                                                                           10585                                                                                           |
|  イベント ソース   |                                                                                          ENTSSO                                                                                           |
|    コンポーネント    |                                                                                            なし                                                                                            |
|  シンボル名  |                                                                             SSO_WARN_EXPIRED_TICKET_REDEEMED                                                                              |
|  メッセージ テキスト   | チケットのタイムアウト期間の有効期限が切れた後にチケットの引き換えがされています。 この application.%r チケットのタイムアウト値が無効になっているため、これは、許可は、<br /><br /> アプリケーション名: %1 |
  
## <a name="explanation"></a>説明  
 チケットのタイムアウトを有効または無効にすることができます。 ここで、チケット引き換えが行われて、タイムアウト期間の有効期限が切れている場合でも、タイムアウトが無効です。  
  
## <a name="user-action"></a>ユーザーの操作  
 タイムアウトが無効にすることになって、ユーザーの操作の必要はありません。 ただし、この特定のアプリケーションは、タイムアウトが無効であるが認識されなかった場合は、アプリケーションをチェックことを許可することを確認してすぐに。