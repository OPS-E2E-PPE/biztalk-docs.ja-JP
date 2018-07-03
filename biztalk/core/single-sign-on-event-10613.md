---
title: 'シングル サインオン: イベント 10613 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 250f113e0cd60b417cee29d32f8e61fbf38632dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023808"
---
# <a name="single-sign-on-event-10613"></a>シングル サインオン: イベント 10613
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                   エンタープライズ シングル サインオン                                                    |
| 製品バージョン |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    イベント ID     |                                                             10613                                                              |
|  イベント ソース   |                                                             ENTSSO                                                             |
|    コンポーネント    |                                                              なし                                                               |
|  シンボル名  |                                                     SSO_ERROR_RPC_CALLBACK                                                     |
|  メッセージ テキスト   | SSO サーバー アクセスが拒否されました。%r<br /><br /> クライアント ユーザー: 1 %r<br /><br /> RPC 呼び出し情報: %2: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 クライアントから SSO サーバーに対して呼び出しが実行されましたが、受け付けられませんでした。 原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。