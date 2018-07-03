---
title: 'シングル サインオン: イベント 10654 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ca59040b340d033ab6c355c0440378f09d87000
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974483"
---
# <a name="single-sign-on-event-10654"></a>シングル サインオン: イベント 10654
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10654                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            N\A                             |
|  シンボル名  |        SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED         |
|  メッセージ テキスト   |    パスワード同期サーバーへの (Windows の) アクセスは拒否されました。%r     |

## <a name="explanation"></a>説明  
 このエラー イベントは、メッセージが [名前] サーバーに送信されたが、応答がブロックされたことを示します。 原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [パスワード同期](../core/password-synchronization2.md)
