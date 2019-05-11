---
title: シングル サインオン:イベント 10543 |Microsoft Docs
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
ms.openlocfilehash: 4f8a3b284910ea5555085a5617a2d2922d0231f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243387"
---
# <a name="single-sign-on-event-10543"></a>シングル サインオン:イベント 10543
## <a name="details"></a>詳細  

|                 |                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                               エンタープライズ シングル サインオン                                                                |
| 製品バージョン |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                               |
|    イベント ID     |                                                                         10543                                                                          |
|  イベント ソース   |                                                                         ENTSSO                                                                         |
|    コンポーネント    |                                                                           CO                                                                           |
|  シンボル名  |                                                           SSO_WARN_ORIGINAL_TICKET_VALIDATED                                                           |
|  メッセージ テキスト   | 検証が必要なチケットが発行されました。 このアプリケーションの validated.%r せず引き換えることができません。<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、検証が必要なアプリケーション チケットが発行されたことを示します。 検証を行わず、チケットを引き換えることはできません。 チケットの検証は、関連アプリケーションごと。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- エンタープライズ シングル サインオンを使用する場合は、メッセージが 信頼されたホストのみを介して送信されていることを確認します。 これにより、メッセージのデータの改ざんのリスクが低減されます。  

- 自分のシナリオにより、このアプリケーションの検証をオフにします。 検証は、管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることです。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケット](../core/sso-tickets.md)  

- [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
