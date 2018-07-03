---
title: 'シングル サインオン: イベント 10543 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf5c026384bf463f6ee0a33045dd1e7b1fca4188
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998449"
---
# <a name="single-sign-on-event-10543"></a>シングル サインオン: イベント 10543
## <a name="details"></a>詳細  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                               エンタープライズ シングル サインオン                                                                |
| 製品バージョン |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    イベント ID     |                                                                         10543                                                                          |
|  イベント ソース   |                                                                         ENTSSO                                                                         |
|    コンポーネント    |                                                                           CO                                                                           |
|  シンボル名  |                                                           SSO_WARN_ORIGINAL_TICKET_VALIDATED                                                           |
|  メッセージ テキスト   | チケットは検証が必要な状態で発行されました。 検証を行わない場合、このアプリケーションと引き換えることはできません。%r<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション チケットが検証が必要な状態で発行されたことを示します。 チケットを引き換えるには、検証する必要があります。 チケットの検証は、関連アプリケーションごとに行われます。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   

- エンタープライズ シングル サインオンを使用している場合は、メッセージが信頼されているホストのみを介して送信されていることを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  

- シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。 検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO チケット](../core/sso-tickets.md)  

- [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
