---
title: SAP アダプターと BizTalk Server でのセキュリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials, protecting
- Enterprise Single Sign-On
- security, when using BizTalk Server
- security, protecting credentials
- SSO
ms.assetid: 702cd0f9-d8e1-4dad-8774-b552481d5390
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4689424deced097d901464263d75e5ae10e4b99f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217778"
---
# <a name="security-with-the-sap-adapter-and-biztalk-server"></a>SAP アダプターと BizTalk Server でのセキュリティ
BizTalk Server 管理コンソールを使用して、コンソールまたはを使用して、送信ポートまたは受信ポート (場所) を構成するときに、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するには、SAP システムの資格情報を指定する必要があります。 悪意のある相手に公開されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックで最も安全に資格情報を指定する方法について説明します、[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの一般的な詳細については、拡張性のあるトピックではこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法については、次を参照してください。、[セキュリティで保護し、BizTalk メッセージを保護](../../core/secure-and-protect-your-biztalk-messages.md)です。  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>どのように保護する資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドインでは、サービスを提供しますか?  
 使用すると、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するユーザー名と、SAP システムのパスワードを指定する必要があります。 行う必要がありますのみから、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。 こうことで、資格情報は表示されません、 **Uri**のフィールド、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]  ダイアログ ボックスで、コンピューター画面にアクセスできる人が読み取ることができます。 使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください、SAP システムのユーザー名とパスワードを入力する方法を含む[Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)です。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合は、または受信場所ですか?  
 BizTalk ソリューションでは、Microsoft BizTalk Wcf-custom アダプターを使用して、WCF サービスを使用します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は、WCF のカスタム バインドを WCF サービスの場合と同様に、SAP システムを使用するクライアントを有効にします。 BizTalk ソリューションの使用、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を通じて送信ポートおよび受信場所を使用するように構成は、さらに、Wcf-custom アダプターを使用して構成されている、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]トランスポートとして。 受信ポート (受信場所)、Wcf-custom アダプターを構成する方法を含む送信ポートを構成する方法の詳細については、次を参照してください。 [SAP アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)です。  
  
 SAP システムの資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの送信ポートまたはから、**他**のタブ**WCF カスタム トランスポート プロパティ**のダイアログ ボックスの受信場所。 WCF カスタム アダプターでは、エンタープライズ シングル サインオン (SSO) をサポートするためにこれらのタブのいずれかのいずれかのユーザー名とパスワード、または SSO 関連アプリケーションを提供することもできます。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワードの資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報** タブ (送信ポート) または**他の** タブ (受信場所) で、 **WCF カスタム トランスポート プロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、 **Uri**  ダイアログ ボックスのフィールドです。 これを防止を画面にアクセス権を持つユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている)、資格情報を表示します。  
  
-   送信ポートをエクスポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルには書き込まれません。 これによりすべてのユーザーからアクセス権を持つファイルにパスワードを表示します。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 WCF カスタム アダプターは SSO を使用して、SAP システムの資格情報を取得するを構成することができます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報にマップするサービスも提供します。 SSO を使用すると、ユーザー名と SAP システムでパスワードを Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*にバックエンド システムへの資格情報をマップします。 関連アプリケーションは、システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する SSO の論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 これは、セカンダリ資格情報をそのアカウント関連システムまたはアプリケーションにアクセスするために使用する Windows アカウントをマップします。 SSO マッピングは、Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]次を行う必要があります。  
  
1.  ユーザーに、SAP システムのパスワードの資格情報の名前を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループ マッピングのユーザー名を使用する Windows アカウントにマップする関連アプリケーションと、SAP システムとの接続を確立するために使用されるパスワードを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特別な種類の SSO 管理者特権を持つユーザーが必要な場合があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは SSO データベースから、SAP のユーザー名とパスワードを取得する SSO によって提供されるサービスを使用します。 これには、これら (暗号化されていない)、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]アダプターは、SAP システムへの接続を開くことができます。 SSO はない暗号化または保護全体にわたる間の接続、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と SAP システムです。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、次を参照してください。[を使用して SSO](../../core/using-sso.md)です。 SSO の概要については、次を参照してください。[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)です。  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、SAP システムの資格情報は、接続 URI で許可されているかどうかを判断します。 既定では、 **AcceptCredentialsInUri**は**false**と[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]URI に資格情報が含まれている場合に例外をスローします。  
  
 URI の接続に存在するための資格情報を必要とする特定のプログラミング シナリオがあるために、このプロパティは確認できます。 送信ポートまたは受信場所を構成するとき、またはを使用している場合にこのことは避けてください、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 このような場合はお勧め設定しないこと**AcceptCredentialsInUri**に**true**です。 詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドのプロパティを参照してください[ORacle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 **AcceptCredentialsInUri**プロパティのバインドでは使用できません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で、**バインディング**Wcf-custom または WCF SAP を構成中にタブ受信または送信ポート。 値を設定する、 **AcceptCredentialsInUri**バインディング プロパティを使用してメタデータを生成した後に作成される、アダプターのバインド ファイル (XML ファイル) を開く必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を見つけて選択し、このバインディングのプロパティにファイル。 このバインドのプロパティに適切な値を指定、バインド ファイルを保存し、バインド ファイルをインポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 参照してください[を再利用の SAP アダプターのバインド](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)手順についてはします。  
  
## <a name="see-also"></a>参照  
[SAP アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
 [SAP アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   