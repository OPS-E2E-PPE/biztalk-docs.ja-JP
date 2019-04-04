---
title: 単一、SOAP アダプターのシングル サインオンのサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, SOAP adapters
- SOAP adapters, SharePoint Portal Server
- SOAP adapters, SSO
- SharePoint Portal server
ms.assetid: c7bf755c-c37d-4b19-9817-a7f42e1e9656
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a95673e0f8d7f8a49ba0ad6d5ba6760a6db4b524
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966707"
---
# <a name="single-sign-on-support-for-the-soap-adapter"></a>SOAP アダプターのシングル サインオン サポート
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、SOAP 受信場所または送信ポートで使用するエンタープライズ シングル サインオン (SSO) を構成できます。 ここでは、SSO と SOAP アダプターの連携について説明します。  
  
 **受信場所の SOAP のシングル サインオン サポート**  
  
 SOAP 受信場所では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンタープライズ SSO と、Microsoft SharePoint Portal Server SSO という 2 種類の SSO がサポートされます。 SharePoint Portal Server SSO のサポートを有効にするには、BizTalk Web サービス公開ウィザードを実行します。 SharePoint Portal Server SSO が有効にする方法の詳細については、[Web サービスの公開](../core/publishing-web-services.md)を参照してください。 BizTalk エンタープライズ シングル サインオンを有効にするには、SOAP 受信場所のプロパティ ページを使用します。 SOAP 受信場所のエンタープライズ SSO を有効にする方法の詳細については、[SOAP 受信場所を構成する方法](../core/how-to-configure-a-soap-receive-location.md)を参照してください。  
  
 **受信場所の SOAP のエンタープライズ SSO のサポート**  
  
 インターネット インフォメーション サービス (IIS) では Web クライアントから SOAP 要求を受信し、ユーザーを認証した後、SOAP アダプターにセキュリティ識別子を渡します。 IIS の認証方法がダイジェスト認証、基本認証、統合 Windows 認証のいずれかである場合、暗号化されたチケットを取得するために、認証を受けたユーザーに基づいて SSO 資格情報ストアが呼び出されます。 このチケットとして格納されている、 **SSOTicket**メッセージのコンテキスト プロパティのプロパティ。  
  
 パススルー シナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。 送信アダプターでは、メッセージ ボックス データベースからメッセージを受信すると、暗号化されたチケットおよびアプリケーション名を指定して RedeemTicket メソッドを呼び出し、そのアプリケーションで使用するセキュリティ資格情報を SSO ストアから取得します。 その後、外部の資格情報を使用してアプリケーションに接続し、SOAP 要求が処理されます。 関連アプリケーションの詳細については、[SSO 関連アプリケーション](../core/sso-affiliate-applications.md)を参照してください。  
  
 オーケストレーションが送信アダプターを呼び出すシナリオでは、BizTalk メッセージング エンジンによって、メッセージ ボックス データベースにメッセージが送信されます。 オーケストレーションで、ことを確認します両方、 **SSOTicket**コンテキスト プロパティと**Microsoft.BizTalk.XLANGs.BTXEngine.OriginatorSID**チケットを格納しているメッセージのコンテキスト プロパティには維持されます。 HTTP アダプターでは、メッセージ ボックス データベースからこのメッセージを受信すると、暗号化されたチケットを指定して RedeemTicket メソッドを呼び出し、バックエンドの資格情報を SSO ストアから取得します。 オーケストレーションをデザインするユーザーは、このプロパティをメッセージに明示的にコピーしてください。  
  
 **受信場所の SOAP の SharePoint Portal Server SSO のサポート**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を SharePoint Portal Server と統合している場合、SOAP アダプター経由でのみ Microsoft SharePoint Portal Server SSO の使用がサポートされます。 SharePoint Portal Server では SSO チケットを作成し、SOAP 要求の SOAP ヘッダーに格納して BizTalk Server に送信します。 チケットとして格納されている SOAP アダプタは、SSO チケットを格納している要求を受信したときに、 **SSOTicket**メッセージのコンテキスト プロパティのプロパティ。 このプロパティには、エンタープライズ SSO チケットも格納されます。 1 つの BizTalk メッセージには、1 つの SSO チケットのみを関連付けることができます。  
  
 パススルーおよびオーケストレーションのシナリオで SharePoint Portal Server から受信した SSO チケットは、エンタープライズ SSO を使用して SOAP アダプターで作成されたチケットと同様に処理されます。 送信アダプターはメッセージを受信、呼び出し、 **RedeemTicket**メソッドを暗号化されたチケットを SharePoint Portal Server が生成されます。 異なる種類の SSO チケットが存在していることを送信アダプターで認識する必要はありません。 **RedeemTicket**メソッドはどの SSO システムには、チケットが生成されたかを判断し、適切な場所から商品と引き換えます。  
  
 **エンタープライズの併用 SSO と SharePoint Portal Server SSO**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、両方の SSO システムの同時使用をサポートしています。 それぞれの SSO で生成したチケットを API で区別できるので、適切な SSO データベースで引き換えることができます。 次の規則が、SOAP 受信される SSO チケットを判断すると同時に両方の SSO システムを使用する場合の場所が昇格する、 **SSOTicket**コンテキストのプロパティ。  
  
- いずれの SSO も有効でない場合、チケットを昇格しません。  
  
- エンタープライズ SSO が有効であり、SharePoint Portal Server SSO が有効でない場合、エンタープライズ SSO チケットを取得して昇格します。  
  
- SharePoint Portal Server SSO が有効であり、エンタープライズ SSO が有効でない場合、既存の SharePoint Portal Server SSO チケットを昇格します。  
  
- エンタープライズ SSO と SharePoint Portal Server SSO がともに有効である場合、さらに次の規則が適用されます。  
  
  -   SharePoint Portal Server SSO チケットを受信した場合、そのチケットを昇格します。  
  
  -   SharePoint Portal Server SSO チケットを受信していない場合、エンタープライズ SSO チケットを取得して昇格します。  
  
  **SOAP 送信アダプタのシングル サインオン サポート**  
  
  SSO が有効になっている場合と SOAP 送信ポートを含むメッセージを受信、 **Secure**プロパティ (**SSOTicket**)、SSO サーバーを検証し、関連アプリケーションのチケットを引き換えるを呼び出します。 SSO を呼び出してチケットを引き換える作業は、関連アプリケーションのアプリケーション管理者、関連管理者、または SSO 管理者が行います。 その後、SSO によってチケットが解読され、バックエンド資格情報を取得します。 パススルーおよびオーケストレーションのシナリオは、SOAP 送信ポートの同じトピックの「Enterprise SSO サポートの SOAP 受信場所」セクションで説明した[、SOAP アダプターのシングル サインオン サポート](../core/single-sign-on-support-for-the-soap-adapter.md)します。  
  
  既定では、SOAP 送信ポートの SSO は有効になっていません。 SOAP 送信ポートの SSO を有効にする方法の詳細については、[SOAP 送信ポートを構成する方法](../core/how-to-configure-a-soap-send-port.md)を参照してください。