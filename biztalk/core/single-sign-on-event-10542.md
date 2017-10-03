---
title: "シングル サインオン: イベント 10542 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8e12444-b47c-4919-85b6-85c8e33b8342
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ebcf97a9de014d0651c9f239c1ae6e846925f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10542"></a>シングル サインオン: イベント 10542
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10542|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_APP_TICKETS_VALIDATED|  
|メッセージ テキスト|チケットの検証を行わない場合、このアプリケーションと引き換えることはできません。%r<br /><br /> アプリケーション名: %1|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション チケットを検証しないと引き換えできないことを示します。 アプリケーション チケットを引き換えるときは、検証を受けることも、受けないようにすることもできます。 検証により、チケットを発行したユーザーの名前と BizTalk メッセージ内のユーザーの名前を比較することで、セキュリティが強化されます。 名前が一致しないと、検証は失敗します。 BizTalk メッセージが信頼されないホストを経由する場合、BizTalk メッセージ内のユーザーの名前は、信頼されないホストのユーザーに変更されます。 検証により、信頼されるホスト経由でのみ BizTalk メッセージが送信されることが保証されます。 このメッセージは、アプリケーション システム レベルで検証が必要であるが (SSO システム オプションの設定による)、呼び出し元によって検証情報が提供されていなかったことを意味します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   BizTalk Server を使用している場合、メッセージは信頼されるホストのみを経由することを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  
  
-   シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。 検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO チケット](../core/sso-tickets.md)  
  
-   [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)