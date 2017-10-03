---
title: "シングル サインオンと BizTalk Adapter TIBCO Enterprise Message Service for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, processing requests
- Single Sign-On, using with adapter
- processing requests
- HTTP requests, processing
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181e54426d568857a9116aa47022adbc7788edaf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a>シングル サインオンおよび BizTalk Adapter for TIBCO Enterprise Message Service
TIBCO Enterprise Message Service (EMS) 用 Microsoft BizTalk Adapter のシングル サインオン (SSO) を使用する場合、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。  
  
 デザイン時には、アダプターが、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。 このユーザーは、アプリケーション ユーザーである必要があります。 実行時には、SSO を使用するときにパススルーのシナリオで受信場所として Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。 このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。  
  
 次に、メッセージがメッセージ ボックス データベースに転送されます。 BizTalk Adapter for TIBCO EMS は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得します。 その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。  
  
> [!NOTE]
>  SSO の構成は BizTalk Server のセットアップの一部として行います。 SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications5.md)   
 [シングル サインオンを使用します。](../core/using-single-sign-on4.md)