---
title: JD Edwards EnterpriseOne の 1 つのシングル サインオンと BizTalk Adapter |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, Single Sign-On
- Single Sign-On, JD Edwards EnterpriseOne adapters
- adapters [JD Edwards EnterpriseOne adapters], Single Sign-On
ms.assetid: efcc3a2d-18a6-4090-9e95-143fb7a356b2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83fefe6ae447a5f68c9516e6fb92ab6e1c0b0614
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393029"
---
# <a name="single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone"></a>JD Edwards EnterpriseOne の 1 つのシングル サインオンと BizTalk Adapter
シングル サインオン (SSO) を Microsoft Adapter for JD Edwards EnterpriseOne を使用する場合、アダプターは SSO 資格情報データベースから資格情報を取得します。 そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。  
  
 デザイン時に、BizTalk Adapter for JD Edwards EnterpriseOne が開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]プロジェクト。 そのユーザーは、アプリケーション ユーザーである必要があります。 実行時に、使用、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターが SSO を使用する場合は、パススルーのシナリオで受信場所として。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。 このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。  
  
 メッセージは、メッセージ ボックス データベースに送られます。 BizTalk Adapter for JD Edwards EnterpriseOne では、メッセージ ボックス データベースからメッセージを受け取るときに呼び出す`ValidateAndRedeemTicket`ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。 次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。  
  
> [!NOTE]
>  SSO の構成は、BizTalk Server のセットアップの一部です。 SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications4.md)   
 [BizTalk Adapter for JD Edwards EnterpriseOne のセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)