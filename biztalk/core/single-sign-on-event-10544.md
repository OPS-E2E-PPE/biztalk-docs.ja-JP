---
title: 'シングル サインオン: イベント 10544 |Microsoft Docs'
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
ms.openlocfilehash: f476e664d50d05a57f42006ec08aa03d901e9f1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983931"
---
# <a name="single-sign-on-event-10544"></a>シングル サインオン: イベント 10544
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10544                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |                  SSO_WARN_TICKET_EXPIRED                   |
|  メッセージ テキスト   | チケットの有効期限が切れました。%r<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション チケットのタイムアウトの期限が切れたことを示します。 システム レベルと、アプリケーション レベルの両方では、チケットのタイムアウトを指定できます。 システム レベルとアプリケーション レベルの両方でタイムアウトが指定されている場合、アプリケーション レベルのタイムアウトが有効期限の決定に使用されます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   

- チケットが検証される前に期限切れになった理由を確認します。  

- チケットのタイムアウト値がチケットの発行時からチケットの引き換え時まで存続するのに十分な長さであることを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO チケット](../core/sso-tickets.md)  

- [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)
