---
title: "シングル サインオン: イベント 10654 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49372d5a-8136-4bdd-8004-b5736ddbe058
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06d7de49ec1606c7c0a33f802af11af4e8ad2848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10654"></a>シングル サインオン: イベント 10654
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10654|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_PS_WINDOWS_CALLBACK_ACCESS_DENIED|  
|メッセージ テキスト|パスワード同期サーバーへの (Windows の) アクセスは拒否されました。%r|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、メッセージが [名前] サーバーに送信されたが、応答がブロックされたことを示します。 原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   このメッセージの情報と、イベント ログで関連情報に注意してください、マイクロソフト製品サポート サービスにお問い合わせください。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [パスワード同期](../core/password-synchronization2.md)