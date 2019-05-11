---
title: 1 つの WCF アダプターのシングル サインオンのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF adapters, Single Sign-On
- Single Sign-On, WCF adapters
ms.assetid: 70a33d87-50bd-41de-9084-68dd66b0dbf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebbe98182d1bc2e97b2ee46245a6d23bfdbe719
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399265"
---
# <a name="single-sign-on-support-for-the-wcf-adapters"></a>WCF アダプタのシングル サインオンのサポート
場所または送信ポートを BizTalk 管理コンソールを使用して受信する WCF で使用するは、エンタープライズ シングル サインオン (SSO) を構成することができます。 このトピックでは、WCF アダプタで SSO のしくみについて説明します。  
  
 ユーザーは、さまざまなシステムやアプリケーションと操作、エンタープライズ環境では、環境が複数のプロセス、製品、およびコンピューター、ユーザー コンテキストを保持しない可能性があります。 このユーザー コンテキストは、元の要求を開始したユーザーを確認する必要があるため、シングル サインオン機能を提供するために非常に重要です。 この問題を解決するために、エンタープライズ シングル サインオン (SSO) には、SSO チケットが用意されており、アプリケーションで元の要求を行ったユーザーに対応する資格情報を取得する際に使用できます。このチケットは Kerberos チケットではありません。  
  
 受信アダプターでは、メッセージが取得されるときに、アダプターは SSO サーバーから SSO チケットを要求できます。 この暗号化されたチケットが含まれています、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]要求と、タイムアウト期間を加えたユーザーの id。 チケットが取得された後、受信メッセージにプロパティとして追加されます。 送信アダプターがメッセージを転送する場合、アダプターは、発行された SSO チケットおよびアダプターが資格情報を取得しようとする関連アプリケーション名、SSO サーバーを接続します。 SSO サーバーでは、ターゲットの関連アプリケーションのユーザーの資格情報を検索し、送信アダプターを使用して関連アプリケーションに適切に認証されたメッセージを送信する資格情報を返します。  
  
## <a name="single-sign-on-support-for-the-wcf-receive-locations"></a>受信場所の WCF のシングル サインオン サポート  
 受信場所に使用される WCF アダプターの種類と組み合わせる適用されるセキュリティ設定は、WCF 受信アダプターが SSO チケットを発行できるかどうかを決定します。 WCF 受信アダプターが SSO トークンを発行する、WCF クライアントが、アダプターが偽装できる資格情報を送信する必要があります。 権限借用は、クライアントの id で実行するサーバー アプリケーションの機能です。 有効な資格情報をマップする必要があります[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]適切な権限借用のためのユーザー アカウント。  
  
> [!NOTE]
>  セキュリティ設定と権限借用の資格情報を送信するようにクライアントを要求しない WCF アダプタは、カスタム受信パイプライン コンポーネントで、クライアントが送信される資格情報の種類と、SSO チケットを発行できます。 SSO のチケットを処理する方法については、受信パイプライン コンポーネントをサンプル パイプライン コンポーネント InPipelineComp を記載を参照してください[サービス指向ソリューションのファイルの在庫](../core/file-inventory-for-the-service-oriented-solution.md)します。  
  
 **受信場所が Wcf-basichttp 用のシングル サインオンのサポート**  
  
 Wcf-basichttp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行することができます。  
  
> [!NOTE]
>  証明書のマッピングの詳細については、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ユーザー アカウントである「ユーザー アカウントに証明書のマッピング」を参照してください[ http://go.microsoft.com/fwlink/?LinkId=87478](http://go.microsoft.com/fwlink/?LinkId=87478)します。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|Basic|なし|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|Ntlm|なし|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|UserName|  
|メッセージ|なし|Certificate|  
|TransportWithMessageCredential|なし|Certificate|  
|TransportWithMessageCredential|なし|UserName|  
|TransportCredentialOnly|Basic|なし|  
|TransportCredentialOnly|ダイジェスト|なし|  
|TransportCredentialOnly|Ntlm|なし|  
|TransportCredentialOnly|Windows|なし|  
|TransportCredentialOnly|Certificate|なし|  
  
 **受信場所、Wcf-wshttp のシングル サインオン サポート**  
  
 Wcf-wshttp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行することができます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|Basic|なし|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|Ntlm|なし|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|UserName|  
|メッセージ|なし|Windows|  
|メッセージ|なし|Certificate|  
|TransportWithMessageCredential|なし|Windows|  
|TransportWithMessageCredential|なし|Certificate|  
|TransportWithMessageCredential|なし|UserName|  
  
 **受信場所、Wcf-nettcp のシングル サインオン サポート**  
  
 Wcf-nettcp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行することができます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|Certificate|  
|メッセージ|なし|Windows|  
|メッセージ|なし|UserName|  
|TransportWithMessageCredential|なし|Certificate|  
|TransportWithMessageCredential|なし|Windows|  
|TransportWithMessageCredential|なし|UserName|  
  
 S**シングル Wcf-netnamedpipe 受信場所のシングル サインオン サポート**  
  
 Wcf-netnamedpipe 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行することができます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|なし|なし|  
  
 **受信場所の Wcf-custom と Wcf-customisolated のシングル サインオン サポート**  
  
 Wcf-custom および Wcf-customisolated 受信場所の SSO チケットを発行するため、受信場所で使用されるセキュリティ設定には、Windows Communication Foundation が偽装できる資格情報を送信する WCF クライアントが必要があります。 WCF では、さまざまな種類のクライアントの資格情報の偽装をサポートします。 WCF では、権限借用の資格情報の種類の詳細についてを参照してください"の委任と偽装と WCF" [ http://go.microsoft.com/fwlink/?LinkId=87476](http://go.microsoft.com/fwlink/?LinkId=87476)します。  
  
## <a name="single-sign-on-support-for-the-wcf-send-ports"></a>WCF 送信ポート用のシングル サインオンのサポート  
 WCF 送信ポートでは、次の表に示すセキュリティ構成でのみ SSO に使用する関連アプリケーション名を指定できます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|Basic|なし|  
|メッセージ|なし|UserName|  
  
> [!NOTE]
>  WCF 送信ポートを検証し、適切に SSO チケットを引き換える、 **SSOTicket**と**OriginatorSID**コンテキスト プロパティでメッセージを送信できる必要があります。 シングル サインオンが有効になっている受信場所は、これらのプロパティを昇格させるから送信者の[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]アカウント。  
  
## <a name="see-also"></a>参照  
 [Enterprise Single Sign-On](../core/enterprise-single-sign-on2.md)