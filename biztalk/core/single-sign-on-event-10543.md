---
title: "シングル サインオン: イベント 10543 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46b1ffda-a6c1-408c-acb4-074183d697bc
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9bf30640bf61f9c88de3fedbb5727be7a715aa8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10543"></a>シングル サインオン: イベント 10543
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10543|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_ORIGINAL_TICKET_VALIDATED|  
|メッセージ テキスト|チケットは検証が必要な状態で発行されました。 検証を行わない場合、このアプリケーションと引き換えることはできません。%r<br /><br /> アプリケーション名: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション チケットが検証が必要な状態で発行されたことを示します。 チケットを引き換えるには、検証する必要があります。 チケットの検証は、関連アプリケーションごとに行われます。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います:   
  
-   エンタープライズ シングル サインオンを使用している場合は、メッセージが信頼されているホストのみを介して送信されていることを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  
  
-   シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。 検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO チケット](../core/sso-tickets.md)  
  
-   [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)