---
title: "シングル サインオン: イベント 10540 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec48afebfa36411594c28908a233409311e32df9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10540"></a>シングル サインオン: イベント 10540
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10540|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_APP_TICKETS_NOT_ALLOWED|  
|メッセージ テキスト|チケットはこのアプリケーションに対して有効になっていません。%r<br /><br /> アプリケーション名: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、チケット機能がこのアプリケーションで有効になっていないことを示します。 SSO チケットの使用は、SSO アプリケーションごとのオプション機能です。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   アプリケーション管理者に連絡し、この SSO アプリケーションのチケットを有効にしてもらいます。 SSO 管理ツール (GUI またはコマンド ライン) を使用して行うことができます。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO チケット](../core/sso-tickets.md)  
  
-   [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)