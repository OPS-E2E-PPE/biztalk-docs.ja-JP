---
title: シングル サインオン:イベント 10655 |Microsoft Docs
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
ms.openlocfilehash: d357eaf5433823f8b21f6d6a6757f06c59bdbd9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397637"
---
# <a name="single-sign-on-event-10655"></a>シングル サインオン:イベント 10655
## <a name="details"></a>詳細  

|                 |                                                                              |
|-----------------|------------------------------------------------------------------------------|
|  製品名   |                          エンタープライズ シングル サインオン                           |
| 製品バージョン |          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]          |
|    イベント ID     |                                    10655                                     |
|  イベント ソース   |                                    ENTSSO                                    |
|    コンポーネント    |                                     該当なし                                      |
|  シンボル名  |                   SSO_ERROR_PS_PING_CALLBACK_ACCESS_DENIED                   |
|  メッセージ テキスト   | パスワード同期サーバー (ping) 用アクセス denied.%r<br /><br /> クライアント ユーザー: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、[名前] サーバーにメッセージが送信されましたが、応答がブロックされたことを示します。 さまざまなプロトコルが正しくないやサーバー上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期](../core/password-synchronization2.md)
