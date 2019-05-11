---
title: シングル サインオン:イベント 10653 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0d85aca-20d9-4d65-8834-b31eacf143c8
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cfcc58ac3d16696e1d7c3ba3a103f1ecbdf3966
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397659"
---
# <a name="single-sign-on-event-10653"></a>シングル サインオン:イベント 10653
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10653                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            該当なし                             |
|  シンボル名  |        SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED         |
|  メッセージ テキスト   |    パスワード同期サーバー (アダプタ用) へのアクセス denied.%r    |

## <a name="explanation"></a>説明  
 このエラー イベントは、クライアントがサーバーに接続しようとしましたが、呼び出しが拒否されたことを示します。 さまざまなプロトコルが正しくないかが不足しているセキュリティのアクセス許可など、さまざまな理由の可能性があります。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期](../core/password-synchronization2.md)
