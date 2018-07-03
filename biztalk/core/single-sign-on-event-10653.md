---
title: 'シングル サインオン: イベント 10653 |Microsoft Docs'
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
ms.openlocfilehash: a9f0edb3ce5fa7f8fb59c4b65914a9c8b6640adc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969459"
---
# <a name="single-sign-on-event-10653"></a>シングル サインオン: イベント 10653
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10653                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            N\A                             |
|  シンボル名  |        SSO_ERROR_PS_ADAPTER_CALLBACK_ACCESS_DENIED         |
|  メッセージ テキスト   |    パスワード同期サーバーへの (アダプターの) アクセスは拒否されました。%r    |

## <a name="explanation"></a>説明  
 このエラー イベントは、クライアントがサーバーに接続しようとしたが、呼び出しが拒否されたことを示します。 原因として、プロトコルが正しくない、セキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期](../core/password-synchronization2.md)
