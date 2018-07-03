---
title: 'シングル サインオン: イベント 10555 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8af9c663-4aa8-4ca5-be63-d4461a2a8517
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a44b3c72659cec8295e7a6625e7b6d94259283c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000307"
---
# <a name="single-sign-on-event-10555"></a>シングル サインオン: イベント 10555
## <a name="details"></a>詳細  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10555                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                            なし                             |
|  シンボル名  |          SSO_ERROR_SECRET_CALLBACK_ACCESS_DENIED           |
|  メッセージ テキスト   | シークレット サーバー アクセスが拒否されました。%r<br /><br /> クライアント ユーザー: %1 |
  
## <a name="explanation"></a>説明  
 メッセージはサーバーに送信されましたが、応答はブロックされました。 原因として、プロトコルが正しくない、サーバーのセキュリティ アクセス許可が不十分など、さまざまな理由が考えられます。  
  
## <a name="user-action"></a>ユーザーの操作  
 エラー ログの情報をメモに取り、製品サポート サービスにお問い合わせください。