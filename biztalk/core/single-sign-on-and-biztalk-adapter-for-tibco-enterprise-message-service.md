---
title: SSO と BizTalk Adapter for TIBCO Enterprise メッセージ サービス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68e85ceb-bf4c-489a-a2c2-1558e718ceed
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb9d0da66a8088c41e61e9c31d1ee722a76b7170
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392911"
---
# <a name="single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service"></a>シングル サインオンと BizTalk Adapter for TIBCO Enterprise Message Service

## <a name="overview"></a>概要
Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) にシングル サインオン (SSO) を使用すると、アダプターは SSO 資格情報データベースから資格情報を取得します。そのためでサーバー システムのログオン資格情報を入力する必要はありません、**トランスポートのプロパティ** ダイアログ ボックス。  
  
 デザイン時に、アダプターは、BizTalk Server プロジェクトを開始したユーザーのコンテキストで (指定された関連アプリケーション) のシステムの資格情報を取得します。 そのユーザーは、アプリケーション ユーザーである必要があります。 実行時に、Microsoft を使用して、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 受信アダプターが SSO を使用する場合は、パススルーのシナリオで受信場所として。  
  
## <a name="processing-requests"></a>要求の処理  
 インターネット インフォメーション サービス (IIS) Web クライアントから HTTP 要求の受信、IIS は、ユーザーを認証します。 ISAPI 拡張機能では、Windows ユーザーを偽装し、暗号化されたチケットを取得する SSO 資格情報ストアを呼び出します。 このチケットは、メッセージのコンテキストでは、SSOTicket プロパティとして格納されます。  
  
 メッセージは、メッセージ ボックス データベースに送られます。 BizTalk Adapter for TIBCO EMS は、メッセージ ボックス データベースからメッセージを受信、ValidateAndRedeemTicket を呼び出し、ログオン資格情報を SSO ストアから取得する関連アプリケーション名と共に暗号化されたチケットを使用します。 次に、アダプターは、システムに接続し、要求を処理する外部資格情報を使用してください。  
  
> [!NOTE]
>  SSO の構成は、BizTalk Server のセットアップの一部です。 SSO エラーが発生した場合は、あるアカウントを使用したドメイン、BizTalk Server を構成したときに、これは、エンタープライズ SSO サービスの機能に影響を確認します。 ドメイン アカウントでの SSO のみ機能します。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションの作成](../core/creating-affiliate-applications5.md)   
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-tibco-ems.md)