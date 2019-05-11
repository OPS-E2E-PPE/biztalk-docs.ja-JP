---
title: Siebel アダプターと BizTalk Server でのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials, security considerations
- security considerations, when using BizTalk Server
- credentials, protecting
- security, protecting credentials when configuring a send port or receive location
- user name password credentials
- security, protecting credentials when using the Consume Adapter Service BizTalk Project Add-in
ms.assetid: 0b3ab81f-0fe3-4dd3-9257-174d9803b4a3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340e8f3616b65602856ef84108fa28198f3d41b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370918"
---
# <a name="security-with-siebel-adapter-and-biztalk-server"></a>Siebel アダプターと BizTalk Server でのセキュリティ
BizTalk Server 管理コンソールを使用して、送信ポートまたは受信ポート (場所) を構成するときに、または使用すると、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するには、Siebel システムの資格情報を指定する必要があります。 可能性のある悪意のあるアクターに開示されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックでは、最も安全に証明書を指定する方法を説明します、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの全般的な説明は包括的なトピックし、はこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法の詳細については、次を参照してください。[セキュリティで保護された、BizTalk メッセージを保護および](../../core/secure-and-protect-your-biztalk-messages.md)します。  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>保護するには資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドイン サービスですか?  
 使用すると、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するユーザー名と Siebel システムのパスワードを指定する必要があります。 これからをのみ行う必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 こうことで、資格情報は表示されません、 **Uri**のフィールド、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]  ダイアログ ボックスで、コンピューターの画面にアクセスできる人が読み取ることができます。 使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください、Siebel システムのユーザー名とパスワードを入力する方法を含む[Visual Studio で Siebel 操作のメタデータの取得](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)します。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合、受信場所でしょうか。  
 BizTalk ソリューションでは、Microsoft BizTalk Wcf-custom アダプターを使用して、WCF サービスを使用します。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]により、クライアントを WCF サービスの場合と同様に、Siebel システムを使用する WCF カスタム バインドは、します。 BizTalk ソリューションの使用、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を通じて送信ポートおよび受信場所を使用するように構成、さらに、Wcf-custom アダプタを使用して構成されている、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]トランスポートとして。 送信ポートを構成し、受信ポート (受信場所)、WCF カスタム アダプターを構成する方法などの方法の詳細については、次を参照してください。 [Condigure Oracle データベースへのポート バインド ファイルを使用して物理的なポート バインド](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)します。  
  
 Siebel システムの資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ**または送信ポート ダイアログ ボックス、**他**のタブ、**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの受信場所。 Wcf-custom アダプターでは、エンタープライズ シングル サインオン (SSO) をサポートするためにこれらのタブのいずれかのいずれかのユーザー名とパスワード、または SSO 関連アプリケーションを提供することもできます。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワード資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報**(送信ポート) 用のタブまたは**他の** タブ (受信場所) で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、 **Uri**  ダイアログ ボックスのフィールド。 資格情報が表示される画面へのアクセスがあるユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている) できません。  
  
-   エクスポート、送信ポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルに書き込まれません。 ようにアクセスできる人物によるファイルにパスワードを表示します。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 エンタープライズ シングル サインオン (SSO) を使用して、Siebel システムの資格情報を取得する Wcf-custom アダプターを構成することができます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報をセカンダリにマップするサービスも提供します。 SSO を使用すると、ユーザー名とパスワードで Siebel システムに Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*バックエンド システム資格情報にマップします。 関連アプリケーションは、sso システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 Windows アカウントは、そのアカウント関連のシステムまたはアプリケーションへのアクセスを使用してセカンダリの資格情報にマップされます。 SSO マッピングを Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]次を行う必要があります。  
  
1.  ユーザー名の Siebel システムのパスワード資格情報を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループ マッピングのユーザー名に、Windows アカウントをマップする関連アプリケーションと Siebel システムへの接続を確立するために使用されるパスワードを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特殊な種類の SSO 管理者特権を持つユーザーが必要があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは、Siebel のユーザー名とパスワードを SSO データベースから取得する SSO によって提供されるサービスを使用します。 これら (非暗号化) を提供、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]アダプターは、Siebel システムへの接続を開くことができます。 SSO は暗号化または保護の間の接続間で、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]と Siebel システム。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、次を参照してください。[を使用して SSO](../../core/using-sso.md)します。 SSO の概要については、次を参照してください。[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)します。  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、Siebel システムの資格情報は、接続 URI で許可されているかどうかを決定します。 既定では、 **AcceptCredentialsInUri**は**false** 、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]資格情報が URI に含まれている場合に例外をスローします。  
  
 接続 URI に存在するための資格情報を必要とする特定のプログラミング シナリオがあるために、このプロパティが表示されます。 これは、べきでは大文字と小文字を使用する場合または送信ポートまたは受信場所を構成するときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。 設定しないことをお勧め**AcceptCredentialsInUri**に**true**します。 詳細については、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドのプロパティは、操作を参照してください。 [for Siebel のバインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)します。  
  
 **AcceptCredentialsInUri**プロパティのバインドでご利用いただけません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で、**バインド**Wcf-custom または WCF Siebel 送信ポートを構成するときにタブ。 値を設定する、 **AcceptCredentialsInUri**バインディングのプロパティを使用してメタデータを生成した後に作成されるアダプターのバインド ファイル (XML ファイル) を開く必要があります、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、し、このバインド プロパティを見つけますファイルです。 このバインドのプロパティに適切な値を入力、バインド ファイルを保存し、バインド ファイルをインポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。 [バインドをインポート](../../core/importing-bindings2.md)は適切なリソースです。 
  
## <a name="see-also"></a>参照  
 [Siebel アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-siebel/secure-your-siebel-applications.md)  
[アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)