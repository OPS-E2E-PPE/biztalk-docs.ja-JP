---
title: Oracle E-business Suite アダプターと BizTalk Server でのセキュリティ |Microsoft ドキュメント
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
ms.openlocfilehash: fe73785ee49b260754a35e27f8ffa2ef2bcaa6bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218482"
---
# <a name="security-with-the-oracle-e-business-suite-adapter-and-biztalk-server"></a>Oracle E-business Suite アダプターと BizTalk Server でのセキュリティ
BizTalk Server 管理コンソールを使用して、コンソールまたはを使用して、送信ポートまたは受信ポート (場所) を構成するときに、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するには、Oracle E-business Suite の資格情報を提供する必要があります。 悪意のある相手に公開されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックで最も安全に資格情報を指定する方法について説明します、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの一般的な詳細については、拡張性のあるトピックではこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法については、次を参照してください。[セキュリティで保護し、BizTalk メッセージを保護](../../core/secure-and-protect-your-biztalk-messages.md)です。   
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in-or-add-adapter-metadata-wizard"></a>どのように保護する資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドインでは、サービスまたはアダプター メタデータのウィザードを追加しますか?  
 使用すると、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]BizTalk ソリューションのメッセージ スキーマを取得するには、次の 2 か所で Oracle E-business Suite への接続に資格情報を提供できます。  
  
-   **セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 こうことで、資格情報は表示されません、 **URI の構成**のフィールド、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]  ダイアログ ボックスで、コンピューター画面にアクセスできる人が読み取ることができます。  
  
-   **OracleUserName**と**OraclePassword**バインドのプロパティ、**バインド プロパティ** タブで、**アダプターの構成**ダイアログ ボックス。 セキュリティ上の理由、 **OraclePassword**バインディング プロパティは使用した結果として生成されたバインド ファイル (XML) ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
    > [!NOTE]
    >  使用して、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]バインド ファイルを生成しません。  
  
 使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]を参照してください[Visual Studio での Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)です。  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合は、または受信場所ですか?  
 BizTalk ソリューションでは、WCF サービスを使用するのに、Microsoft BizTalk Wcf-custom アダプターまたは WCF Oracle EBS アダプターを使用します。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を WCF サービスの場合と同様に、Oracle E-business Suite を使用するクライアントを有効にする WCF バインドは、します。 BizTalk ソリューションの使用、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を通じて送信ポートおよび受信場所を使用するように構成は、さらに、Wcf-custom または Wcf-oracleebs アダプターを使用して構成されている、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]トランスポートとして。 受信ポート (受信場所)、Wcf-custom アダプターを構成する方法を含む送信ポートを構成する方法の詳細については、次を参照してください。 [Oracle データベースへのポートのバインド ファイルを使用して物理ポートのバインドを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)です。  
  
 Oracle E-business Suite の資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの送信ポートまたはから、**他**タブ、 **Wcf-custom トランスポートのプロパティ**のダイアログ ボックスの受信場所。 Wcf-custom アダプターまたは WCF Oracle EBS アダプターは、エンタープライズ シングル サインオン (SSO) をサポートするため、ユーザー名とパスワードを入力することもできます。 または SSO 関連アプリケーションにこれらのタブのいずれか。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワードの資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報** タブ (送信ポート) または**他の** タブ (受信場所) で、 **WCF カスタム トランスポート プロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、**アドレス (URI)**  ダイアログ ボックスのフィールドです。 これを防止を画面にアクセス権を持つユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている)、資格情報を表示します。  
  
-   送信ポートをエクスポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルには書き込まれません。 これによりすべてのユーザーからアクセス権を持つファイルにパスワードを表示します。  
  
### <a name="oraclepassword-binding-property"></a>OraclePassword バインディング プロパティ  
 指定した値、 **OraclePassword**バインディング プロパティの送信または受信ポートは、BizTalk Server のアプリケーションからバインドをエクスポートするときにクリア テキストで利用できます。 そのため、BizTalk Server のアプリケーションからバインド ファイルをエクスポートした後にする必要がありますを手動で削除の値、 **OraclePassword**バインド ファイルからプロパティをバインドし、各ホストでもう一度指定場所、エクスポートされるバインドが使用されます。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 Oracle E-business Suite の資格情報を取得するエンタープライズ シングル サインオン (SSO) を使用する Wcf-custom アダプターを構成することができます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報にマップするサービスも提供します。 SSO を使用すると、ユーザー名と Oracle データベースでのパスワードを Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*にバックエンド システムへの資格情報をマップします。 関連アプリケーションは、システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する SSO の論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 これは、セカンダリ資格情報をそのアカウント関連システムまたはアプリケーションにアクセスするために使用する Windows アカウントをマップします。 SSO マッピングは、Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次を行う必要があります。  
  
1.  Oracle E-business Suite のユーザー名パスワードの資格情報を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループのマッピングのユーザー名を使用する Windows アカウントにマップする関連アプリケーションと、Oracle データベースとの接続を確立するために使用されるパスワードを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特別な種類の SSO 管理者特権を持つユーザーが必要な場合があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは SSO データベースから Oracle ユーザー名とパスワードを取得する SSO によって提供されるサービスを使用します。 これには、これら (暗号化されていない)、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アダプターは、Oracle E-business Suite への接続を開くことができます。 SSO はない暗号化または保護全体にわたる間の接続、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]と Oracle E-business Suite です。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、次を参照してください。[を使用して SSO](../../core/using-sso.md)です。 SSO の概要については、次を参照してください。[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)です。 
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]サーフェス、 **AcceptCredentialsInUri**プロパティをバインドします。 このプロパティは、Oracle データベースまたは Oracle E-business Suite の資格情報は、接続 URI で許可されているかどうかを判断します。 既定では、 **AcceptCredentialsInUri**は**false**と[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]URI に資格情報が含まれている場合に例外をスローします。  
  
 URI の接続に存在するための資格情報を必要とする特定のプログラミング シナリオがあるために、このプロパティは確認できます。 送信ポートまたは受信場所を構成するとき、またはを使用している場合にこのことは避けてください、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]からのメッセージ スキーマを取得する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 設定しないことをお勧め**AcceptCredentialsInUri**に**true**です。 詳細については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドのプロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
 **AcceptCredentialsInUri**プロパティのバインドでは使用できません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]で、**バインディング**Wcf-custom の構成中にタブ Wcf-oracleebs 受信または送信ポートまたはします。 値を設定する、 **AcceptCredentialsInUri**バインディング プロパティを使用してメタデータを生成した後に作成される、アダプターのバインド ファイル (XML ファイル) を開く必要があります、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を見つけて選択し、このバインディングのプロパティにファイル。 このバインドのプロパティに適切な値を指定、バインド ファイルを保存し、バインド ファイルをインポート[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。 参照してください[バインドのインポート](http://msdn.microsoft.com/library/7af35a2e-fb7c-48a1-af28-93427403a745)手順についてはします。  
  
## <a name="see-also"></a>参照  
 [Oracle EBS アプリケーションのセキュリティ保護します。](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)  
 [Oracle EBS アダプターをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)
