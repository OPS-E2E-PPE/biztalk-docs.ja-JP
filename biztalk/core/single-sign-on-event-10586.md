---
title: "シングル サインオン: イベント 10586 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 124ed0a722d0da0f21722f3b337c8bb938068b24
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10586"></a>シングル サインオン: イベント 10586
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10586|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_CRED_CACHE_OFF|  
|メッセージ テキスト|この SSO サーバーについて資格情報キャッシュが無効になっています。|  
  
## <a name="explanation"></a>説明  
 一般的には有効になっている資格情報キャッシュが無効になっていました。 資格情報キャッシュを有効または無効にできるのはシステム管理者だけです。 資格情報キャッシュを無効にすると、パフォーマンスが低下する可能性がありますが、ENTSSO システムから、より新しい資格情報が取得されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 資格情報のキャッシュを再度有効にするには、」の関連アプリケーションのプロパティのテーブルを参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。