---
title: SQL アダプターと BizTalk Server でのセキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc439d65-1d7e-4e6e-bb0d-a8cb9f0607b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179051a8d9522ca760780c7a7f1060789129724e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367934"
---
# <a name="security-with-the-sql-adapter-and-biztalk-server"></a>SQL アダプターと BizTalk Server でのセキュリティ
コンソール、BizTalk Server 管理を使用して、送信ポートまたは受信ポート (場所) を構成するときに、またはを使用して、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] BizTalk ソリューションのメッセージ スキーマを取得する SQL Server データベースの資格情報を指定する必要があります。 可能性のある悪意のあるアクターに開示されるを防ぐためにセキュリティで保護された方法でこれらの資格情報を提供する重要です。 このトピックでは、最も安全に証明書を指定する方法を説明します、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]の BizTalk Server ソリューションです。  
  
 BizTalk ソリューションのコンテキストでのセキュリティの全般的な説明は包括的なトピックし、はこのドキュメントの範囲外です。 作成する方法、BizTalk ソリューションより安全な方法の詳細については、次を参照してください。[セキュリティで保護された、BizTalk メッセージを保護および](../../core/secure-and-protect-your-biztalk-messages.md)します。
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>保護するには資格情報を使用する場合、アダプターを使用する BizTalk プロジェクト アドイン サービスですか?  
 使用すると、 [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのメッセージ スキーマを取得するユーザー名とパスワードを指定する必要があります、**セキュリティ** タブで、**アダプターの構成** ダイアログ ボックス。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]で資格情報を設定することはできません、 **URI の構成**フィールド。 これにより、資格情報がクリア テキストで表示されるようにすることでセキュリティが向上します。 使用してメッセージ スキーマを取得する方法について、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]を参照してください、SQL Server データベースのユーザー名とパスワードを入力する方法を含む[SQLアダプタを使用してVisualStudioでSQLServer操作のメタデータを取得](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>資格情報を保護する方法、送信ポートを構成する場合、受信場所でしょうか。  
 BizTalk ソリューションでは、Microsoft BizTalk Wcf-custom アダプターを使用して、WCF サービスを使用します。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]により、クライアントを WCF サービスの場合と同様に、SQL Server データベースを使用する WCF カスタム バインドは、します。 BizTalk ソリューションの使用、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を通じて送信ポートおよび受信場所を Wcf-custom アダプターを使用して構成されています。 Wcf-custom アダプターでは、使用するように構成、さらに、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]トランスポートとして。 送信ポートを構成し、受信ポート (受信場所)、WCF カスタム アダプターを構成する方法などの方法の詳細については、次を参照してください。 [SQL アダプターを物理ポートのバインドを手動で構成](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)します。
  
 SQL Server データベースの資格情報を構成する、**資格情報**のタブ、 **Wcf-custom トランスポートのプロパティ**または送信ポート ダイアログ ボックス、**他**のタブ**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスの受信場所。 Wcf-custom アダプターでは、エンタープライズ シングル サインオン (SSO) をサポートするためにこれらのタブのいずれかのいずれかのユーザー名とパスワード、または SSO 関連アプリケーションを提供することもできます。 次のトピックでは、両方のオプションについて説明します。  
  
### <a name="user-name-password-credentials"></a>ユーザー名パスワード資格情報  
 ユーザー名とパスワードを指定する必要がありますのみ、**資格情報**(送信ポート) 用のタブまたは**他の** タブ (受信場所) で、 **Wcf-custom トランスポートのプロパティ** ダイアログ ボックス。 これにより、次に。  
  
-   資格情報は表示されません、**アドレス (URI)**  ダイアログ ボックスのフィールド。 資格情報が表示される画面へのアクセスがあるユーザー (または送信ポートを表示または受信場所のプロパティを可能にするアクセス許可を持っている) できません。  
  
-   エクスポート、送信ポートまたはポートのバインドを受信する場合、パスワードは、バインド ファイルに書き込まれません。 ようにアクセスできる人物によるファイルにパスワードを表示します。  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>エンタープライズ シングル サインオンと SSO 関連アプリケーション  
 SQL Server データベースの資格情報を取得するエンタープライズ シングル サインオン (SSO) を使用するように、Wcf-custom アダプターを構成できます。 SSO では、データベースとマスター シークレットを使用して暗号化およびユーザーの資格情報を格納します。 Microsoft Windows アカウントをバックエンド システムへのアクセスに使用される資格情報をセカンダリにマップするサービスも提供します。 SSO を使用すると、ユーザー名と SQL Server データベースのパスワードを Windows アカウントをマップできます。  
  
 SSO を使用して*関連アプリケーション*と*SSO マッピング*バックエンド システム資格情報にマップします。 関連アプリケーションは、sso システムまたはセカンダリの資格情報を必要とするアプリケーションを参照する論理エンティティです。 SSO マッピングは、関連アプリケーションに関連付けられます。 Windows アカウントは、そのアカウント関連のシステムまたはアプリケーションへのアクセスを使用してセカンダリの資格情報にマップされます。 SSO マッピングを Windows ユーザー アカウントまたはグループに関連付けることができます。  
  
 SSO を使用する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]次を行う必要があります。  
  
1.  ユーザーに、SQL Server データベースの名前のパスワード資格情報を保持するために sso 関連アプリケーションを作成します。 この手順は多くの場合、特別な種類の SSO 管理者特権を持つユーザーによって実行します。  
  
2.  ユーザーまたはグループ マッピングのユーザー名と SQL Server データベースとの接続を確立するために使用されるパスワードに、Windows アカウントをマップする関連アプリケーションを作成します。 インストールに応じて、ユーザーは、この手順を実行できる場合があります。 または特殊な種類の SSO 管理者特権を持つユーザーが必要があります。  
  
> [!NOTE]
>  SSO で構成された場合、WCF カスタム アダプターは、SSO データベースから SQL Server ユーザー名とパスワードを取得する SSO によって提供されるサービスを使用します。 これら (非暗号化) を提供、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]アダプターは、SQL Server データベースへの接続を開くことができます。 SSO は暗号化または保護の間の接続間で、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]と SQL Server データベース。  
  
 関連アプリケーションと SSO マッピングを作成する方法に関する情報など、SSO を使用する方法については、次を参照してください。[を使用して SSO](../../core/using-sso.md)します。 SSO の概要については、次を参照してください。[を実装するエンタープライズ シングル サインオン](../../core/implementing-enterprise-single-sign-on.md)します。
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>AcceptCredentialsInUri バインディング プロパティ  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]はサポートしていません**AcceptCredentialsInUri**プロパティをバインドします。 資格情報は、接続 URI では使用されません。  
  
## <a name="see-also"></a>参照  
[SQL アプリケーションをセキュリティで保護する](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[SQL アダプタをセキュリティで保護するベスト プラクティス](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)