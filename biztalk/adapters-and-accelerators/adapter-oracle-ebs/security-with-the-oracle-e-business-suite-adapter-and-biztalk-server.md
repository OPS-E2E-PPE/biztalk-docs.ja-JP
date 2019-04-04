---
title: Oracle E-business Suite アダプターと BizTalk Server でのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d4a816c-505d-4d5d-9eb9-04847f9b5861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 066ee0946210bc313188de200e695a684138e560
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752922"
---
# <a name="security-with-the-oracle-e-business-suite-adapter-and-biztalk-server"></a>Oracle E-business Suite アダプターと BizTalk Server でのセキュリティ
コンソール、BizTalk Server 管理を使用して、送信ポートまたは受信ポート (場所) を構成するときに、またはを使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得する、Oracle E-business Suite の資格情報を指定する必要があります。 可能性のある悪意のあるアクターに開示されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックでは、最も安全に証明書を指定する方法を説明します、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの全般的な説明は包括的なトピックし、はこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法の詳細については、[セキュリティで保護された、BizTalk メッセージを保護および](../../core/secure-and-protect-your-biztalk-messages.md)を参照してください。   
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in-or-add-adapter-metadata-wizard"></a>保護するには資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドイン サービスまたはアダプター メタデータのウィザードを追加しますか?  
 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk ソリューションのメッセージ スキーマを取得するには、次の 2 つの場所での Oracle E-business Suite への接続に資格情報を指定できます。  
  
- **セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 こうことで、資格情報は表示されません、 **URI の構成**のフィールド、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]  ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。  
  
- **OracleUserName**と**OraclePassword**バインドのプロパティ、**バインド プロパティ** タブで、**アダプターの構成**ダイアログ ボックス。 セキュリティ上の理由から、 **OraclePassword**プロパティのバインドでは利用できませんを使用した結果生成されたバインド ファイル (XML ファイル) ファイル、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
  > [!NOTE]
  >  使用して、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]バインド ファイルを生成しません。  
  
  使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)します。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合、受信場所でしょうか。  
 BizTalk ソリューションでは、Microsoft BizTalk Wcf-custom または WCF Oracle EBS アダプターを使用して、WCF サービスを使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]により、クライアントを WCF サービスの場合と同様に、Oracle E-business Suite を使用する WCF バインドは、します。 BizTalk ソリューションの使用、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を通じて送信ポートおよび受信場所を使用するように構成、さらに、Wcf-custom または Wcf-oracleebs アダプターを使用して構成されている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]トランスポートとして。 送信ポートを構成し、受信ポート (受信場所)、WCF カスタム アダプターを構成する方法などの方法の詳細については、[Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインドを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)を参照してください。  

 Oracle E-business Suite の資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ**または送信ポート ダイアログ ボックス、**他**タブ、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの受信場所。 Wcf-custom または WCF Oracle EBS アダプターでは、エンタープライズ シングル サインオン (SSO) をサポートするため、ユーザー名とパスワードを提供することもできます。 または SSO 関連アプリケーションでこれらのタブのいずれか。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワード資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報**(送信ポート) 用のタブまたは**他の** タブ (受信場所) で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、**アドレス (URI)**  ダイアログ ボックスのフィールド。 資格情報が表示される画面へのアクセスがあるユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている) できません。  
  
-   エクスポート、送信ポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルに書き込まれません。 これができなくからアクセス権を持つファイルにパスワードを表示します。  
  
### <a name="oraclepassword-binding-property"></a>OraclePassword バインディング プロパティ  
 指定した値、 **OraclePassword**送信プロパティのバインドまたは受信ポートは、BizTalk Server でのアプリケーションからバインドをエクスポートするときにクリア テキストで使用できます。 そのため、BizTalk Server でのアプリケーションからバインド ファイルをエクスポートした後にする必要があります手動で削除するの値、 **OraclePassword**バインド ファイルからプロパティをバインドし、各ホストでもう一度指定場所、エクスポートされるバインドが使用されます。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 エンタープライズ シングル サインオン (SSO) を使用して、Oracle E-business Suite の資格情報を取得する Wcf-custom アダプターを構成することができます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報をセカンダリにマップするサービスも提供します。 SSO を使用すると、ユーザー名と Oracle データベースでのパスワードを Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*バックエンド システム資格情報にマップします。 関連アプリケーションは、sso システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 Windows アカウントは、そのアカウント関連のシステムまたはアプリケーションへのアクセスを使用してセカンダリの資格情報にマップされます。 SSO マッピングを Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次を行う必要があります。  
  
1.  Oracle E-business suite、ユーザー名パスワードの資格情報を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループ マッピングの関連アプリケーションのユーザー名に、Windows アカウントをマップして、Oracle データベースとの接続を確立するために使用されるパスワードを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特殊な種類の SSO 管理者特権を持つユーザーが必要があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは SSO データベースから Oracle ユーザー名とパスワードを取得する SSO によって提供されるサービスを使用します。 これら (非暗号化) を提供、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプターは、Oracle E-business Suite への接続を開くことができます。 SSO は暗号化または保護の間の接続間で、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と Oracle E-business Suite。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、[を使用して SSO](../../core/using-sso.md)を参照してください。 SSO の概要については、[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)を参照してください。 
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、Oracle データベースまたは Oracle E-business Suite の資格情報は、接続 URI で許可されているかどうかを決定します。 既定では、 **AcceptCredentialsInUri**は**false** 、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]資格情報が URI に含まれている場合に例外をスローします。  
  
 接続 URI に存在するための資格情報を必要とする特定のプログラミング シナリオがあるために、このプロパティが表示されます。 これは、べきでは大文字と小文字を使用する場合または送信ポートまたは受信場所を構成するときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 設定しないことをお勧め**AcceptCredentialsInUri**に**true**します。 詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
 **AcceptCredentialsInUri**プロパティのバインドでご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で、**バインド**Wcf-custom を構成するときにタブ Wcf-oracleebs 受信または送信ポートまたはします。 値を設定する、 **AcceptCredentialsInUri**バインディングのプロパティを使用してメタデータを生成した後に作成されるアダプターのバインド ファイル (XML ファイル) を開く必要があります、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、し、このバインド プロパティを見つけますファイルです。 このバインドのプロパティに適切な値を指定、バインド ファイルを保存し、バインド ファイルをインポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 参照してください[バインドのインポート](http://msdn.microsoft.com/library/7af35a2e-fb7c-48a1-af28-93427403a745)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)  
 [Oracle EBS アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)
