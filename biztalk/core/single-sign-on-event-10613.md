---
title: シングル サインオン:イベント 10613 |Microsoft Docs
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
ms.openlocfilehash: d9a2743e19ef393409df934c811698557e9b0078
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397701"
---
# <a name="single-sign-on-event-10613"></a>シングル サインオン:イベント 10613
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                   エンタープライズ シングル サインオン                                                    |
| 製品バージョン |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    イベント ID     |                                                             10613                                                              |
|  イベント ソース   |                                                             ENTSSO                                                             |
|    コンポーネント    |                                                              なし                                                               |
|  シンボル名  |                                                     SSO_ERROR_RPC_CALLBACK                                                     |
|  メッセージ テキスト   | SSO サーバー アクセス denied.%r<br /><br /> クライアント ユーザー: 1 %r<br /><br /> RPC 呼び出し情報: %2: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 呼び出しは、SSO サーバーにクライアントからしましたが、受け付けられませんでした。 さまざまなプロトコルが正しくないや、クライアント上の不十分なセキュリティ アクセス許可など、さまざまな理由の可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このメッセージの情報と、イベント ログで関連情報をメモし、マイクロソフト製品サポート サービスにお問い合わせください。