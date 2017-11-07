---
title: "PeopleSoft Enterprise の単一のサインオンと BizTalk Adapter |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb898906bfd3087ef909e59990a16ce16c2822c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a>シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise
シングル サインオン (SSO) を Microsoft BizTalk Adapter for PeopleSoft Enterprise を使用するときに、アダプターが SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ**] ダイアログ ボックス。  
  
 デザイン時には、BizTalk Adapter for PeopleSoft Enterprise が、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーションの) システムの資格情報を取得します。 このユーザーは、アプリケーション ユーザーである必要があります。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) は、Web クライアントから HTTP 要求を受信すると、ユーザーを認証します。 ISAPI 拡張が Windows ユーザーの権限を借用し、SSO 資格情報ストアを呼び出して、暗号化されたチケットを取得します。 このチケットは、SSOTicket プロパティとしてメッセージのコンテキストに保存されます。  
  
 次に、メッセージがメッセージ ボックス データベースに転送されます。 BizTalk Adapter for PeopleSoft Enterprises は、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットと関連アプリケーション名を指定して ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得します。 その後、外部の資格情報を使用してシステムに接続し、要求が処理されます。  
  
> [!NOTE]
>  SSO の構成は BizTalk Server のセットアップの一部として行います。 SSO エラーが発生した場合は、ときに使用したドメイン アカウント BizTalk Server を構成したように、エンタープライズ SSO サービスの機能に影響を確認します。 SSO はドメイン アカウントでのみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications2.md)   
 [アダプターをセキュリティで保護します。](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)