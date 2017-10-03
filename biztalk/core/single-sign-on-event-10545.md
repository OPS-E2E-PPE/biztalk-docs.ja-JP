---
title: "シングル サインオン: イベント 10545 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 268cb7be-b191-4335-a4cc-7c15d879507c
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64cb10ceef5827f9c0b0aab5d9810db061af8a71
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10545"></a>シングル サインオン: イベント 10545
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10545|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_ISSUE_TICKETS_NOT_ALLOWED|  
|メッセージ テキスト|SSO システムに対してチケットが有効になっていません。|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、チケットが SSO システムについて有効になっていないことを示します。 チケットをシステム レベルで無効にすると、関連アプリケーション レベルでもチケットを使用できなくなります。 チケットをシステム レベルで有効にして、関連アプリケーション レベルで無効にすることは可能です。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   SSO システム レベルでチケットを有効にします。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO チケット](../core/sso-tickets.md)  
  
-   [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)