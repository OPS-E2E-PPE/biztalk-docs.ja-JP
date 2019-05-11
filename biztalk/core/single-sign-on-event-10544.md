---
title: シングル サインオン:イベント 10544 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c79e2186-1c75-4e7b-8bf5-f582e5c2aac7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 262a57b44143909b40842eddf7b1aba4049ca130
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243506"
---
# <a name="single-sign-on-event-10544"></a>シングル サインオン:イベント 10544
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10544                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |                  SSO_WARN_TICKET_EXPIRED                   |
|  メッセージ テキスト   | チケットが expired.%r<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション チケットのタイムアウトの期限が切れたことを示します。 システム レベルと、アプリケーション レベルの両方では、チケットのタイムアウトを指定できます。 システム レベルとアプリケーション レベルのタイムアウトの両方が指定されている場合は、アプリケーション レベルのタイムアウトが期限の決定に使用されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- チケットが検証される前に期限切れ理由を確認します。  

- チケットのタイムアウト値が引き換えるには、時刻にチケットを発行するときに時間まで存続するのに十分な時間であることを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケット](../core/sso-tickets.md)  

- [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)
