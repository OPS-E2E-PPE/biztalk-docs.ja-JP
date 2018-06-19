---
title: 'シングル サインオン: イベント 10541 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e206158-5652-453c-91ac-9a75ab02809a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 201a43682898f312687f3d5d453f3b050bc75d48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270106"
---
# <a name="single-sign-on-event-10541"></a>シングル サインオン: イベント 10541
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10541|  
|イベント ソース|ENTSSO|  
|コンポーネント|CO|  
|シンボル名|SSO_WARN_SSO_TICKETS_VALIDATED|  
|メッセージ テキスト|チケットを引き換えるには、検証する必要があります。|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO チケットを検証しないと引き換えできないことを示します。 SSO チケットを引き換えるときに、検証できる場合と、検証できない場合があります。 検証により、チケットを発行したユーザーの名前と BizTalk メッセージ内のユーザーの名前を比較することで、セキュリティが強化されます。 名前が一致しないと、検証は失敗します。 BizTalk メッセージが信頼されないホストを経由する場合、BizTalk メッセージ内のユーザーの名前は、信頼されないホストのユーザーに変更されます。 検証により、信頼されるホスト経由でのみ BizTalk メッセージが送信されることが保証されます。 このメッセージは、SSO システム レベルで検証が必要であるが (SSO システム オプションの設定による)、呼び出し元によって検証情報が提供されていなかったことを意味します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   BizTalk Server を使用している場合、メッセージは信頼されるホストのみを経由することを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  
  
-   シナリオで許可される場合は、このアプリケーションに対して検証をオフにしてください。 検証は、システムまたは特定のアプリケーションのみに対してオフにできる管理オプションです。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO チケット](../core/sso-tickets.md)  
  
-   [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  
  
-   [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)