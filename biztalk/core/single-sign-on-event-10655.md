---
title: 'シングル サインオン: イベント 10655 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bb6a8dd-35e4-40a6-8900-450a9b6de249
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ce0442b02667ce9796d9418dae4b1700dd757d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013011"
---
# <a name="single-sign-on-event-10655"></a>シングル サインオン: イベント 10655
## <a name="details"></a>詳細  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  製品名   |                          エンタープライズ シングル サインオン                           |
| 製品バージョン |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    イベント ID     |                                    10655                                     |
|  イベント ソース   |                                    ENTSSO                                    |
|    コンポーネント    |                                     N\A                                      |
|  シンボル名  |                   SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED                   |
|  メッセージ テキスト   | パスワード同期サーバーへの (ping の) アクセスは拒否されました。%r<br /><br /> クライアント ユーザー: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、メッセージが [名前] サーバーに送信されたが、応答がブロックされたことを示します。 原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期](../core/password-synchronization2.md)
