---
title: "シングル サインオンと BizTalk Adapter JD Edwards EnterpriseOne for |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182e73ed45a1473286a301cf859e619cc5d21287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a>シングル サインオンと BizTalk Adapter for JD Edwards EnterpriseOne
Microsoft Adapter for JD Edwards EnterpriseOne でシングル サインオン (SSO) を使用すると、アダプターは SSO 資格情報データベースから資格情報を取得します。 したがって、する必要はありませんでサーバー システムのログオン資格情報を入力する、**トランスポートのプロパティ** ダイアログ ボックス。  
  
 デザイン時には、BizTalk Adapter for JD Edwards OneWorld が、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。 このユーザーは、アプリケーション ユーザーである必要があります。 実行時には、SSO を使用するときにパススルーのシナリオで、受信場所として [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターを使用してください。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、ストアを呼び出して、SSO 資格情報を暗号化されたチケットを取得します。 このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。  
  
 次に、メッセージがメッセージ ボックス データベースに転送されます。 BizTalk Adapter for JD Edwards EnterpriseOne は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して `ValidateAndRedeemTicket` を呼び出し、SSO ストアからログオン資格情報を取得します。 その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。  
  
> [!NOTE]
>  SSO の構成は BizTalk Server のセットアップの一部として行います。 SSO エラーが発生した場合、アカウントを使用したドメイン BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications4.md)   
 [シングル サインオンを使用します。](../core/using-single-sign-on1.md)