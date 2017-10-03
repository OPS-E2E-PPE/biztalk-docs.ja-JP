---
title: "シングル サインオン サポートを SOAP アダプターの |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, SOAP adapters
- SOAP adapters, SharePoint Portal Server
- SOAP adapters, SSO
- SharePoint Portal server
ms.assetid: c7bf755c-c37d-4b19-9817-a7f42e1e9656
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b6e604eaf7e1b0a9b6144dc20f8bdd59d03932f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-support-for-the-soap-adapter"></a>SOAP アダプターのシングル サインオン サポート
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、SOAP 受信場所または送信ポートで使用するエンタープライズ シングル サインオン (SSO) を構成できます。 ここでは、SSO と SOAP アダプターの連携について説明します。  
  
 **シングル サインオン サポートを SOAP の受信場所**  
  
 SOAP 受信場所では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンタープライズ SSO と、Microsoft SharePoint Portal Server SSO という 2 種類の SSO がサポートされます。 SharePoint Portal Server SSO のサポートを有効にするには、BizTalk Web サービス公開ウィザードを実行します。 SharePoint Portal Server SSO の有効化についての詳細については、次を参照してください。 [Web サービスの公開](../core/publishing-web-services.md)です。 BizTalk エンタープライズ シングル サインオンを有効にするには、SOAP 受信場所のプロパティ ページを使用します。 詳細については、SOAP 受信場所のエンタープライズ SSO を有効にすると、次を参照してください。 [SOAP 受信場所を構成する方法](../core/how-to-configure-a-soap-receive-location.md)です。  
  
 **受信場所の SOAP のエンタープライズ SSO のサポート**  
  
 インターネット インフォメーション サービス (IIS) では Web クライアントから SOAP 要求を受信し、ユーザーを認証した後、SOAP アダプターにセキュリティ識別子を渡します。 IIS の認証方法がダイジェスト認証、基本認証、統合 Windows 認証のいずれかである場合、暗号化されたチケットを取得するために、認証を受けたユーザーに基づいて SSO 資格情報ストアが呼び出されます。 このチケットとして格納されている、 **SSOTicket**メッセージのコンテキスト プロパティのプロパティです。  
  
 パススルー シナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。 送信アダプターでは、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットおよびアプリケーション名を指定して RedeemTicket メソッドを呼び出し、そのアプリケーションで使用するセキュリティ資格情報を SSO ストアから取得します。 その後、外部の資格情報を使用してアプリケーションに接続し、SOAP 要求が処理されます。 関連アプリケーションの詳細については、次を参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)です。  
  
 オーケストレーションが送信アダプターを呼び出すシナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。 オーケストレーションで、ことを確認する必要があります両方、 **SSOTicket**コンテキスト プロパティ、および**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**チケットを格納するメッセージのコンテキスト プロパティには保持されます。 HTTP アダプターでは、メッセージ ボックス データベースからこのメッセージを受信すると、暗号化されたチケットを指定して RedeemTicket メソッドを呼び出し、バックエンドの資格情報を SSO ストアから取得します。 オーケストレーションをデザインするユーザーは、このプロパティをメッセージに明示的にコピーしてください。  
  
 **受信場所の SOAP の SharePoint Portal Server SSO のサポート**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を SharePoint Portal Server と統合している場合、SOAP アダプター経由でのみ Microsoft SharePoint Portal Server SSO の使用がサポートされます。 SharePoint Portal Server では SSO チケットを作成し、SOAP 要求の SOAP ヘッダーに格納して BizTalk Server に送信します。 チケットとして格納されている SOAP アダプターでは、SSO チケットを含む要求を受信したときに、 **SSOTicket**メッセージのコンテキスト プロパティのプロパティです。 このプロパティには、エンタープライズ SSO チケットも格納されます。 1 つの BizTalk メッセージには、1 つの SSO チケットのみを関連付けることができます。  
  
 パススルーおよびオーケストレーションのシナリオで SharePoint Portal Server から受信した SSO チケットは、エンタープライズ SSO を使用して SOAP アダプターで作成されたチケットと同様に処理されます。 送信アダプターは、メッセージを受信したときに呼び出し、 **RedeemTicket**メソッドを暗号化されたチケット生成その SharePoint Portal Server です。 異なる種類の SSO チケットが存在していることを送信アダプターで認識する必要はありません。 **RedeemTicket**メソッドどの SSO システムがチケットを生成および制御する適切な場所から引き換えます。  
  
 **エンタープライズの併用 SSO と SharePoint Portal Server SSO**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、両方の SSO システムの同時使用をサポートしています。 それぞれの SSO で生成したチケットを API で区別できるので、適切な SSO データベースで引き換えることができます。 次の規則が、SOAP 受信される SSO チケットを決定する、同時に両方の SSO システムを使用する場合の場所に昇格、 **SSOTicket**コンテキストのプロパティ。  
  
-   いずれの SSO も有効でない場合、チケットを昇格しません。  
  
-   エンタープライズ SSO が有効であり、SharePoint Portal Server SSO が有効でない場合、エンタープライズ SSO チケットを取得して昇格します。  
  
-   SharePoint Portal Server SSO が有効であり、エンタープライズ SSO が有効でない場合、既存の SharePoint Portal Server SSO チケットを昇格します。  
  
-   エンタープライズ SSO と SharePoint Portal Server SSO がともに有効である場合、さらに次の規則が適用されます。  
  
    -   SharePoint Portal Server SSO チケットを受信した場合、そのチケットを昇格します。  
  
    -   SharePoint Portal Server SSO チケットを受信していない場合、エンタープライズ SSO チケットを取得して昇格します。  
  
 **SOAP 送信アダプタのシングル サインオン サポート**  
  
 SSO が有効になっている場合、SOAP 送信ポートが受け取った場合を含むメッセージ、 **Secure**プロパティ (**SSOTicket**)、SSO サーバーを検証し、関連アプリケーションのチケットを引き換える呼び出しです。 SSO を呼び出してチケットを引き換える作業は、関連アプリケーションのアプリケーション管理者、関連管理者、または SSO 管理者が行います。 その後、SSO によってチケットが解読され、バックエンド資格情報を取得します。 パススルーおよびオーケストレーションのシナリオは、SOAP 送信ポートのと同じトピックの「Enterprise SSO サポートの SOAP 受信場所」セクションで説明した[、SOAP アダプターのシングル サインオン サポート](../core/single-sign-on-support-for-the-soap-adapter.md)です。  
  
 既定では、SOAP 送信ポートの SSO は有効になっていません。 SOAP 送信ポートの SSO を有効にする方法の詳細については、次を参照してください。 [SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)です。