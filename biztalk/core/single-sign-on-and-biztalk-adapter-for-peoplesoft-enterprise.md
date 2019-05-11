---
title: シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing HTTP requests
- Single Sign-On, using with the adapter
- HTTP requests, processing
ms.assetid: d8ad75f1-a83f-4722-a43f-50dc95df2f9d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6819b89f7c09fdf347f362f89038e732f6f24396
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393014"
---
# <a name="single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise"></a>シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise
Microsoft BizTalk adapter for PeopleSoft Enterprise のシングル サインオン (SSO) を使用するときに、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。  
  
 デザイン時に、BizTalk Adapter for PeopleSoft Enterprise は、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。 そのユーザーは、アプリケーション ユーザーである必要があります。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出しています。 このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。  
  
 メッセージは、メッセージ ボックス データベースに送られます。 BizTalk Adapter for PeopleSoft Enterprises は、メッセージ ボックス データベースからメッセージを受信、ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。 次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。  
  
> [!NOTE]
>  SSO の構成は、BizTalk Server のセットアップの一部です。 SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications2.md)   
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)