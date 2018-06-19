---
title: Oracle データベース アダプターと BizTalk Server でのセキュリティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user name password credentials
- SSO mapping
- credentials
- credentials, protecting
- credentials, security considerations
- affiliate application
ms.assetid: c7e0be64-4ab9-4ee3-b88a-4f8f5f07b280
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47c4ad584f23b156d2f28397952074d358995136
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216282"
---
# <a name="security-with-the-oracle-database-adapter-and-biztalk-server"></a>Oracle データベース アダプターと BizTalk Server でのセキュリティ
BizTalk Server 管理コンソールを使用して、コンソールまたはを使用して、送信ポートまたは受信ポート (場所) を構成するときに、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するには、Oracle データベースの資格情報を指定する必要があります。 悪意のある相手に公開されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックで最も安全に資格情報を指定する方法について説明します、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの一般的な詳細については、拡張性のあるトピックではこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法については、次を参照してください。[セキュリティで保護し、BizTalk メッセージを保護](../../core/secure-and-protect-your-biztalk-messages.md)です。  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in-or-add-adapter-metadata-wizard"></a>どのように保護する資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドインでは、サービスまたはアダプター メタデータのウィザードを追加しますか?  
 使用すると、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するユーザー名と Oracle データベースのパスワードを指定する必要があります。 行う必要がありますのみから、**セキュリティ**タブで、**アダプターの構成** ダイアログ ボックス。 こうことで、資格情報は表示されません、 **URI の構成**のフィールド、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]  ダイアログ ボックスで、コンピューター画面にアクセスできる人が読み取ることができます。 使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください、Oracle データベースのユーザー名とパスワードを入力する方法を含む[Visual Studio での Oracle 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)です。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合は、または受信場所ですか?  
 BizTalk ソリューションでは、Microsoft BizTalk Wcf-custom アダプターを使用して、WCF サービスを使用します。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]は、WCF のカスタム バインドを WCF サービスの場合と同様に、Oracle データベースを使用するクライアントを有効にします。 BizTalk ソリューションの使用、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を通じて送信ポートおよび受信場所を使用するように構成は、さらに、Wcf-custom アダプターを使用して構成されている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]トランスポートとして。 受信ポート (受信場所)、Wcf-custom アダプターを構成する方法を含む送信ポートを構成する方法の詳細については、次を参照してください。 [Oracle データベース アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md)です。  
  
 Oracle データベースの資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの送信ポートまたはから、**他**のタブ、**Wcf-custom トランスポートのプロパティ**のダイアログ ボックスの受信場所。 WCF カスタム アダプターでは、エンタープライズ シングル サインオン (SSO) をサポートするためにこれらのタブのいずれかのいずれかのユーザー名とパスワード、または SSO 関連アプリケーションを提供することもできます。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワードの資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報** タブ (送信ポート) または**他の** タブ (受信場所) で、 **WCF カスタム トランスポート プロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、**アドレス (URI)**  ダイアログ ボックスのフィールドです。 これを防止を画面にアクセス権を持つユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている)、資格情報を表示します。  
  
-   送信ポートをエクスポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルには書き込まれません。 これによりすべてのユーザーからアクセス権を持つファイルにパスワードを表示します。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 Oracle データベースの資格情報を取得するエンタープライズ シングル サインオン (SSO) を使用する Wcf-custom アダプターを構成することができます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報にマップするサービスも提供します。 SSO を使用すると、ユーザー名と Oracle データベースでのパスワードを Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*にバックエンド システムへの資格情報をマップします。 関連アプリケーションは、システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する SSO の論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 これは、セカンダリ資格情報をそのアカウント関連システムまたはアプリケーションにアクセスするために使用する Windows アカウントをマップします。 SSO マッピングは、Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次を行う必要があります。  
  
1.  ユーザーに、Oracle データベースのパスワードの資格情報の名前を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループのマッピングのユーザー名を使用する Windows アカウントにマップする関連アプリケーションと、Oracle データベースとの接続を確立するために使用されるパスワードを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特別な種類の SSO 管理者特権を持つユーザーが必要な場合があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは SSO データベースから Oracle ユーザー名とパスワードを取得する SSO によって提供されるサービスを使用します。 これには、これら (暗号化されていない)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]アダプターは、Oracle データベースへの接続を開くことができます。 SSO はない暗号化または保護全体にわたる間の接続、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と Oracle データベース。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、次を参照してください。[を使用して SSO](../../core/using-sso.md)です。 SSO の概要については、次を参照してください。[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)です。  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、Oracle データベースの資格情報は、接続 URI で許可されているかどうかを判断します。 既定では、 **AcceptCredentialsInUri**は**false**と[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]URI に資格情報が含まれている場合に例外をスローします。  
  
 URI の接続に存在するための資格情報を必要とする特定のプログラミング シナリオがあるために、このプロパティは確認できます。 送信ポートまたは受信場所を構成するとき、またはを使用している場合にこのことは避けてください、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。 設定しないことをお勧め**AcceptCredentialsInUri**に**true**です。 詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドのプロパティを参照してください[Oracle データベースのバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)です。  
  
 **AcceptCredentialsInUri**プロパティのバインドでは使用できません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で、**バインディング**Wcf-custom または Wcf-oracledb の構成中にタブ受信または送信ポート。 値を設定する、 **AcceptCredentialsInUri**バインディング プロパティを使用してメタデータを生成した後に作成される、アダプターのバインド ファイル (XML ファイル) を開く必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を見つけて選択し、このバインディングのプロパティにファイル。 このバインドのプロパティに適切な値を指定して、バインド ファイルを保存し、BizTalk server バインド ファイルをインポートします。 参照してください[アダプターのバインドが SQL の再利用](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)です。  
  
## <a name="see-also"></a>参照  
 [Oracle データベース アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[ベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)