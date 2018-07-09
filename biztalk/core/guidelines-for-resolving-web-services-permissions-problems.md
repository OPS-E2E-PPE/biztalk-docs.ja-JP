---
title: Web サービスのアクセス許可の問題を解決するためのガイドライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e29543e9-9b87-437b-ac91-8f1cce01fab4
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd4420cb7c651ae1ad1bbe4bcb318b86b59c9ac4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005315"
---
# <a name="guidelines-for-resolving-web-services-permissions-problems"></a><span data-ttu-id="78bec-102">Web サービスの権限の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="78bec-102">Guidelines for Resolving Web Services Permissions Problems</span></span>
<span data-ttu-id="78bec-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には Web サービスが広く採用され、SOAP アダプターで使用したり、オーケストレーションを Web サービスとして公開したりできるようになっています。</span><span class="sxs-lookup"><span data-stu-id="78bec-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] makes extensive use of Web services for use with the SOAP adapter and when publishing orchestrations as Web services.</span></span> <span data-ttu-id="78bec-104">このトピックでは、Web サービスのアクセス許可の問題を最小限に抑えるための一般的なガイドラインを提供し、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に影響を与える Web サービスのアクセス許可の問題をトラブルシューティングするための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="78bec-104">This topic provides some general guidelines for minimizing Web services permissions problems and steps that you can follow to troubleshoot Web services permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="78bec-105">一般的なガイドライン</span><span class="sxs-lookup"><span data-stu-id="78bec-105">General Guidelines</span></span>  
  
- <span data-ttu-id="78bec-106">**ユーザー アカウントの設定**: Web サービスをホストする仮想ディレクトリに関連付けられた IIS アプリケーション ホスト プロセス id が特定のユーザー アカウントに設定されていることを確認し、このユーザー アカウントが次のグループに追加されるようにします。</span><span class="sxs-lookup"><span data-stu-id="78bec-106">**Setting user accounts**: Ensure that the IIS application host process identity associated with the virtual directory that hosts the Web service is set to a specific user account and ensure that this user account is added to the following groups:</span></span>  
  
  - <span data-ttu-id="78bec-107">BizTalk 分離ホスト ユーザー (ドメインまたはローカル グループ)</span><span class="sxs-lookup"><span data-stu-id="78bec-107">BizTalk Isolated Host Users (domain or local group)</span></span>  
  
  - <span data-ttu-id="78bec-108">IIS_WPG (ローカル グループ)</span><span class="sxs-lookup"><span data-stu-id="78bec-108">IIS_WPG (local group)</span></span>  
  
    <span data-ttu-id="78bec-109">BizTalk Web サービス公開ウィザードで作成された Web サービスに、BizTalk メッセージ ボックス データベースに SOAP 要求メッセージを公開する (これにより、サブスクライブを行うオーケストレーションをアクティブ化する) ための適切な権限を与えるには、これら 2 つのグループのメンバーシップが必要です。</span><span class="sxs-lookup"><span data-stu-id="78bec-109">Membership in these 2 groups is required to grant the Web service created by the BizTalk Web Service Publishing Wizard the appropriate rights to publish a SOAP request message into the BizTalk MessageBox database which will in turn activate the subscribing orchestration.</span></span> <span data-ttu-id="78bec-110">決定または IIS アプリケーション ホスト プロセス id の設定の詳細については、次を参照してください、 **IIS アプリケーション ホスト プロセス Id の設定**の[にIISのアクセス許可問題を解決するためのガイドライン。](../core/guidelines-for-resolving-iis-permissions-problems.md).</span><span class="sxs-lookup"><span data-stu-id="78bec-110">For more information about determining or setting the IIS application host process identity, see the **Setting IIS Application Host Process Identity** section of [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md).</span></span>  
  
- <span data-ttu-id="78bec-111">**TEMP 環境変数によって指定されたフォルダーのアクセス許可設定**: Web サービスをホストする仮想ディレクトリの IIS アプリケーション ホスト プロセス id の読み取りがあることを確認し、によって指定されたフォルダーに対する書き込みアクセス許可、TEMP 環境変数。</span><span class="sxs-lookup"><span data-stu-id="78bec-111">**Setting permissions on the folder specified by the TEMP environment variable**: Ensure that the IIS application host process identity for the virtual directory that hosts the Web service has read and write permissions to the folder specified by the TEMP environment variable.</span></span> <span data-ttu-id="78bec-112">TEMP 環境変数によって指定されているフォルダーを確認するには、BizTalk Server でコマンド プロンプトを開き、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="78bec-112">To determine the folder that is specified by the TEMP environment variable open a command prompt on the BizTalk Server, type the following command, and then press ENTER:</span></span>  
  
  ```  
  echo %TEMP%  
  ```  
  
   <span data-ttu-id="78bec-113">TEMP 環境変数によって指定されたフォルダーは、Web サービスがダイナミック リンク ライブラリ (dll) ファイル形式に Just In Time (JIT) コンパイルされる場所であるため、このユーザー アカウントが読み取り/書き込みアクセス許可を使用してアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="78bec-113">The folder specified by the TEMP environment variable is where the Web service is Just In Time (JIT) compiled into a dynamic link library (dll) file and therefore must be accessible with read and write permissions by this user account.</span></span>  
  
- <span data-ttu-id="78bec-114">**SOAP メソッドの呼び出しで資格情報を送信する**: Web サービス クライアントが SOAP メソッドの呼び出しで資格情報を送信していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="78bec-114">**Sending credentials in the SOAP method call**: Ensure that the Web service client is sending credentials in the SOAP method call.</span></span> <span data-ttu-id="78bec-115">既定では、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の IIS 7.0 では Windows 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="78bec-115">By default IIS 7.0 in [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] requires windows authentication.</span></span> <span data-ttu-id="78bec-116">Internet Explorer を使用して Web サービスをテストするときは、現在ログオンしているユーザーの資格情報が自動的に送信されます。このため、Web サービスは、Internet Explorer からは機能していても、別のクライアントからは機能していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="78bec-116">When testing a Web service with Internet Explorer, the credentials of the user who is currently logged on are automatically sent which is why the Web service may work from Internet Explorer but fail from another client.</span></span> <span data-ttu-id="78bec-117">Web サービス クライアントが SOAP メソッドの呼び出しに資格情報を追加しない場合、認証の失敗によって SOAP 例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="78bec-117">If the Web service client does not add credentials to the SOAP method call a SOAP exception will be generated due to an authentication failure.</span></span> <span data-ttu-id="78bec-118">SOAP メソッドの資格情報の送信の詳細については、呼び出しで使用可能なサンプル コードを参照してください。[新しい System.Net クラスを使用して HTTP クライアントを作成する方法](http://support.microsoft.com/kb/303436)します。</span><span class="sxs-lookup"><span data-stu-id="78bec-118">For more information about sending credentials in a SOAP method call see the sample code available in [How to use the new System.Net classes to create an HTTP client](http://support.microsoft.com/kb/303436).</span></span>  
  
- <span data-ttu-id="78bec-119">**Web サービスの呼び出しエラーのトラブルシューティング**: Web サービスを呼び出すときにエラーが発生した場合、アプリケーション ログを確認するかメッセージを BizTalk Server 管理イベントとサービス インスタンスの追跡**グループ ハブ**ページ。</span><span class="sxs-lookup"><span data-stu-id="78bec-119">**Troubleshooting errors calling a Web service**: If errors occur when calling a Web service, check the Application log, or message event and service instance tracking through the BizTalk Server Administration **Group Hub** page.</span></span> <span data-ttu-id="78bec-120">エラーの考えられる原因の詳細については、次を参照してください。 [BizTalk Server の監視](../core/monitoring-biztalk-server.md)と[グループ ハブ ページを使用して](../core/using-the-group-hub-page.md)します。</span><span class="sxs-lookup"><span data-stu-id="78bec-120">For more information about the possible causes of the error, see [Monitoring BizTalk Server](../core/monitoring-biztalk-server.md) and [Using the Group Hub Page](../core/using-the-group-hub-page.md).</span></span>  
  
- <span data-ttu-id="78bec-121">**デバッグ情報の収集**: 詳細なデバッグ情報を取得するトピックに記載されている手順に従います[公開 Web サービスのデバッグ](../core/debugging-published-web-services.md)上記の手順に従っても問題が解決しない場合。</span><span class="sxs-lookup"><span data-stu-id="78bec-121">**Collecting debugging information**: To obtain detailed debugging information, follow the steps outlined in the topic [Debugging Published Web Services](../core/debugging-published-web-services.md) if following the steps above does not resolve the issue.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="78bec-122">既知の問題</span><span class="sxs-lookup"><span data-stu-id="78bec-122">Known Issues</span></span>  
 <span data-ttu-id="78bec-123">に関する既知の問題に関する追加情報について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスのアクセス許可に関連してを参照してください「BizTalk Server を実行しているサーバー上の Web サービスとして公開されているオーケストレーションを呼び出すことはできません」 [ http://go.microsoft.com/fwlink/?LinkId=196379 ](http://go.microsoft.com/fwlink/?LinkId=196379).</span><span class="sxs-lookup"><span data-stu-id="78bec-123">For additional information on known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] related to Web services permissions, see "You cannot call an orchestration that is exposed as a Web service on a server that is running BizTalk Server" at [http://go.microsoft.com/fwlink/?LinkId=196379](http://go.microsoft.com/fwlink/?LinkId=196379).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bec-124">参照</span><span class="sxs-lookup"><span data-stu-id="78bec-124">See Also</span></span>  
 <span data-ttu-id="78bec-125">[BizTalk Server のアクセス許可のトラブルシューティング](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="78bec-125">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="78bec-126">IIS のアクセス許可の問題を解決するためのガイドライン</span><span class="sxs-lookup"><span data-stu-id="78bec-126">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)