---
title: "手順 3: ドメイン コント ローラーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, domain controller
- domain controller
ms.assetid: 1c513225-378b-4e57-ba29-7532b6cbcc9a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad3cdf84f5a392a8d5f836e78c57f782e14d0639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configuring-the-domain-controller"></a>手順 3: ドメイン コント ローラーの構成
このセクションのドメイン コント ローラーを構成する方法を説明する、[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]展開します。 具体的には、このセクションの内容がインストールおよび構成する方法について説明します[!INCLUDE[btsAD](../../includes/btsad-md.md)]次の手順で。  
  
-   Active Directory と DNS をインストールします。  
  
-   必要なアカウントを作成します。  
  
-   ドメインに参加します。  
  
## <a name="installing-active-directory-and-dns"></a>Active Directory と DNS をインストールします。  
 使用して、[!INCLUDE[btsAD](../../includes/btsad-md.md)]インストール ウィザードをドメイン コント ローラーを構成するプロセスを簡略化します。 Active Directory をインストールすると、ドメイン ネーム システム (DNS) の逆引き参照ゾーンを作成します。 作成し、正引きおよび逆引き参照ゾーンにホストを追加します。  
  
## <a name="creating-the-required-accounts"></a>必要なアカウントを作成します。  
 次の表は、グローバル セキュリティ グループを作成する方法の詳細を提供します。 次の作成**グローバル セキュリティ**グループと、独自の名前付け規則を使用してドメイン コント ローラー上のユーザーです。 以下の例は、わかりやすくするために使用されます。 作成されたグループを一覧で、指定したメンバーを追加します。  
  
 グループを作成するときに選択**グローバル**グループのスコープと**セキュリティ**グループの種類のです。  
  
|アカウントまたはグループの名前|型|Description|メンバー|  
|---------------------------|----------|-----------------|-------------|  
|管理|ユーザー|すべての BizTalk コンピューター、ドメイン コント ローラーと SQL Server を実行しているすべてのコンピューターのローカル管理者アカウント。<br /><br /> これは、アプリケーションのインストールに使用されるドメイン ユーザー アカウント ([!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]、 [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]、および SQL Server) および A4SWIFT のデザイン時に BizTalk Accelerator を構成するためです。 A4SWIFT のインストールを実行するドメイン管理者特権を持っている必要はありません。 管理者ユーザー アカウントが Domain Users グループ、ドメインの BizTalk Server 管理者グループ、およびローカルの Administrators グループのメンバーにする必要があります。||  
|SQLSvc|ユーザー|SQL Server サービスを実行するためのアカウント||  
|SSOSvc|ユーザー|シングル サインオン (SSO) サービスを実行するためのアカウント||  
|HostSvc|ユーザー|BizTalk ホスト サービスを実行するためのアカウント||  
|IsolatedSvc|ユーザー|BizTalk の分離サービスを実行するためのアカウント||  
|BAMSvc|ユーザー|BAMPortal、BAMAlerts、および BAMTools の BizTalk Server の構成に必要な||  
|BRESvc|ユーザー|ルール エンジン更新サービスのサービスを実行するためのアカウント||  
|Domain Admins|ドメイン グループ|ドメイン管理者のグローバル ドメイン グループ アカウント||  
|BizTalk 分離ホスト ユーザー|ドメイン グループ|BizTalk 分離ホスト (ホスト プロセスが HTTP および SOAP など、BizTalk Server で実行されていない) へのアクセスを持つアカウントのグローバル ドメイン グループです。|\<IsolatedSvc >、 \<HostSvc >|  
|BizTalk Server 管理者|ドメイン グループ|フレームワークの構成ウィザードに含まれる管理タスクを実行して、BizTalk Server を管理するために必要な最小限の特権を持つグローバル ドメイン グループ アカウント。|\<Admin >|  
|BizTalk Application Users|ドメイン グループ|BizTalk アプリケーション ユーザーのグローバル ドメイン グループ アカウント。|\<HostSvc >|  
|BizTalk Server オペレータ|ドメイン グループ|インストールした後、BizTalk Server 環境を操作するために必要なタスクを実行するために必要な最低限の権限を持つグループです。||  
|SharePoint 対応ホスト|ドメイン グループ|Windows SharePoint Services アダプター Web サービスを呼び出すアクセス許可を持つ Windows グループ。|\<HostSvc >|  
|SSO 管理者|ドメイン グループ|SSO 管理者のグローバル ドメイン グループ アカウント。|\<Admin >、 \<SSOSvc >|  
|SSO 関連管理者|ドメイン グループ|グローバル ドメイン グループ アカウントの SSO 関連管理者|\<Admin >|  
|A4SWIFT のユーザー|ドメイン グループ|A4SWIFT の基本的なタスクを実行するために必要な最小限の特権を持つグローバル ドメイン グループ アカウント。|\<HostSvc >、追加のユーザーのネットワーク|  
|A4SWIFT の管理者|ドメイン グループ|A4SWIFT を管理するために必要な最小限の特権を持つグローバル ドメイン グループ アカウント。|\<Admin >|  
  
> [!NOTE]
>  すべてのグループ アカウントは、グローバル セキュリティ アカウントとローカルではないドメイン アカウントにする必要があります。 (Net localgroup を使用して作成される) のローカル ドメイン グループ アカウントを使用している場合、セットアップ プログラム[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]特定を検証できません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ドメイン ユーザー。  
  
## <a name="joining-the-domain"></a>ドメインに参加します。  
 作成した後、ドメインおよびドメイン コント ローラーを再起動して、各サーバーをドメインに参加させます。