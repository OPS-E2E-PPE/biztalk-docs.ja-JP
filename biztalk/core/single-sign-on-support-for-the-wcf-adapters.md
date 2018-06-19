---
title: 単一の WCF アダプタのサインオンのサポート |Microsoft ドキュメント
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
ms.openlocfilehash: 712aa01190762d6c6f74604a5f48c19fe42531d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280058"
---
# <a name="single-sign-on-support-for-the-wcf-adapters"></a>WCF アダプターのシングル サインオンのサポート
BizTalk 管理コンソールを使用して、WCF 受信場所または送信ポートで使用するエンタープライズ シングル サインオン (SSO) を構成できます。 ここでは、SSO と WCF アダプターの連携について説明します。  
  
 ユーザーがさまざまなシステムおよびアプリケーションを操作するエンタープライズ環境では、複数のプロセス、製品、およびコンピューターでユーザー コンテキストが保持されないことがよくあります。 このユーザー コンテキストは、元の要求を開始したユーザーを確認する必要があるために、シングル サインオン機能を提供するために重要です。 この問題を解決するために、エンタープライズ シングル サインオン (SSO) には、SSO チケットが用意されており、アプリケーションで元の要求を行ったユーザーに対応する資格情報を取得する際に使用できます。このチケットは Kerberos チケットではありません。  
  
 受信アダプターでメッセージが取得されると、アダプターは SSO サーバーから SSO チケットを要求できます。 この暗号化されたチケットには、要求を行ったユーザーの [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] ID と、タイムアウト期間が含まれます。 チケットが取得されると、チケットは受信メッセージにプロパティとして追加されます。 メッセージの送信時、送信アダプターは、発行された SSO チケットおよびアダプターが資格情報を取得しようとする関連アプリケーション名を使用して、SSO サーバーに問い合わせます。 SSO サーバーは対象の関連アプリケーションのユーザー資格情報を参照した後、その資格情報を送信アダプターに返します。送信アダプターはその資格情報を使用して、適切に認証されたメッセージを関連アプリケーションに送信します。  
  
## <a name="single-sign-on-support-for-the-wcf-receive-locations"></a>WCF 受信場所のシングル サインオンのサポート  
 適用されるセキュリティ設定と、受信場所に使用される WCF アダプターの種類の組み合わせにより、WCF 受信アダプターが SSO チケットを発行できるかどうかが決まります。 WCF 受信場所が SSO トークンを発行するには、WCF クライアントはアダプターが偽装できる資格情報を送信する必要があります。 偽装とは、サーバー アプリケーションがクライアントの ID を使用できることを意味します。 適切な偽装を行うには、資格情報を有効な [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] ユーザー アカウントにマップする必要があります。  
  
> [!NOTE]
>  クライアントに偽装のための資格情報の送信を要求しないセキュリティ設定と WCF アダプターの場合、クライアントがカスタム受信パイプライン コンポーネントで送信する任意の種類の資格情報を使用して、SSO チケットを発行できます。 受信パイプライン コンポーネントで SSO チケットを処理する方法についての詳細、サンプル パイプライン コンポーネント InPipelineComp に含まれるを参照してください[サービス指向ソリューションのファイル一覧](../core/file-inventory-for-the-service-oriented-solution.md)です。  
  
 **受信場所が Wcf-basichttp 用のシングル サインオンのサポート**  
  
 WCF-BasicHttp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行できます。  
  
> [!NOTE]
>  証明書のマッピングの詳細については、[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ユーザー アカウントに「のユーザー アカウントに証明書のマッピング」を参照してください[http://go.microsoft.com/fwlink/?LinkId=87478](http://go.microsoft.com/fwlink/?LinkId=87478)です。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|基本|なし|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|Ntlm|なし|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|UserName|  
|メッセージ|なし|Certificate|  
|[TransportWithMessageCredential]|なし|Certificate|  
|[TransportWithMessageCredential]|なし|UserName|  
|TransportCredentialOnly|基本|なし|  
|TransportCredentialOnly|ダイジェスト|なし|  
|TransportCredentialOnly|Ntlm|なし|  
|TransportCredentialOnly|Windows|なし|  
|TransportCredentialOnly|Certificate|なし|  
  
 **受信場所、Wcf-wshttp のシングル サインオン サポート**  
  
 WCF-WSHttp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行できます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|基本|なし|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|Ntlm|なし|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|UserName|  
|メッセージ|なし|Windows|  
|メッセージ|なし|Certificate|  
|[TransportWithMessageCredential]|なし|Windows|  
|[TransportWithMessageCredential]|なし|Certificate|  
|[TransportWithMessageCredential]|なし|UserName|  
  
 **受信場所の WCF-NetTcp のシングル サインオン サポート**  
  
 WCF-NetTcp 受信アダプターは、次の表に示すセキュリティ構成でのみ SSO サーバーから SSO チケットを発行できます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|Windows|なし|  
|[Transport]|Certificate|なし|  
|メッセージ|なし|Certificate|  
|メッセージ|なし|Windows|  
|メッセージ|なし|UserName|  
|[TransportWithMessageCredential]|なし|Certificate|  
|[TransportWithMessageCredential]|なし|Windows|  
|[TransportWithMessageCredential]|なし|UserName|  
  
 S**シングル サインオン サポートを Wcf-netnamedpipe 受信場所に対して**  
  
 WCF-NetNamedPipe 受信アダプターは、次の表に示すセキュリティ構成でのみ、SSO サーバーから SSO チケットを発行できます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|なし|なし|  
  
 **シングル サインオン サポートを Wcf-custom と Wcf-customisolated の受信場所**  
  
 WCF-Custom および WCF-CustomIsolated 受信場所が SSO チケットを発行するには、受信場所で使用されるセキュリティ設定で、Windows Communication Foundation が偽装できる資格情報を WCF クライアントから送信するようにします。 WCF は、さまざまな種類のクライアント資格情報の偽装をサポートしています。 WCF では、権限借用の資格情報の種類の詳細についてを参照してください"委任と偽装と WCF" [http://go.microsoft.com/fwlink/?LinkId=87476](http://go.microsoft.com/fwlink/?LinkId=87476)です。  
  
## <a name="single-sign-on-support-for-the-wcf-send-ports"></a>WCF 送信ポートのシングル サインオンのサポート  
 WCF 送信ポートでは、次の表に示すセキュリティ構成でのみ、SSO に使用する関連アプリケーション名を指定できます。  
  
|[セキュリティ モード]|トランスポート クライアントの資格情報の種類|証明書|  
|-------------------|--------------------------------------|------------------------------------|  
|[Transport]|ダイジェスト|なし|  
|[Transport]|基本|なし|  
|メッセージ|なし|UserName|  
  
> [!NOTE]
>  WCF 送信ポートを検証し、適切に SSO チケットを引き換える、 **SSOTicket**と**OriginatorSID**コンテキスト プロパティが送信されるメッセージで使用する必要があります。 シングル サインオンが有効になっている受信場所は、これらのプロパティを送信者の [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] アカウントから昇格させることができます。  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオン](../core/enterprise-single-sign-on2.md)