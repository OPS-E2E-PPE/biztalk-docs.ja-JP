---
title: "シングル サインオン: イベント 10613 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a87ca19-24a0-4cf8-984f-2f70d7b5018c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7230a0d6400a7265ef9f3cedb6bb47cc23aade
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10613"></a>シングル サインオン: イベント 10613
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10613|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_RPC_CALLBACK|  
|メッセージ テキスト|SSO サーバー アクセスが拒否されました。%r<br /><br /> クライアント ユーザー: %1 %r<br /><br /> RPC 呼び出し情報: %n%n 2: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 クライアントから SSO サーバーに対して呼び出しが実行されましたが、受け付けられませんでした。 原因として、プロトコルが正しくない、クライアントのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このメッセージの情報と、イベント ログで関連情報に注意してください、マイクロソフト製品サポート サービスにお問い合わせください。