---
title: デプロイのセキュリティの概要 |Microsoft Docs
description: セキュリティ、暗号化、BizTalk Server の展開でユーザー グループについてのクイック リンク
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1c5a000-9f6b-49db-bd87-8c694240a192
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d7e0a1201c6d37e0c30ad898248bcc8d7e895f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002763"
---
# <a name="securing-your-biztalk-server-deployment"></a><span data-ttu-id="b505e-103">BizTalk Server の安全な展開</span><span class="sxs-lookup"><span data-stu-id="b505e-103">Securing Your BizTalk Server Deployment</span></span>
<span data-ttu-id="b505e-104">このセクションのトピックでは、BizTalk をインストールして構成した後の、ファイアウォール ポート、インターネット プロトコル セキュリティ (IPSec)、Secure Sockets Layer (SSL) セキュリティの構成に関するリンクが示されています。</span><span class="sxs-lookup"><span data-stu-id="b505e-104">The topics in this section provide the links about configuring firewall ports, Internet protocol security (IPSec), and secure sockets layer (SSL) security after you have installed and configured BizTalk.</span></span>  
  
- <span data-ttu-id="b505e-105">Web サーバーに SSL を実装する方法の詳細については、[ http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b505e-105">For more information about how to implement SSL in a Web server, see [http://go.microsoft.com/fwlink/p/?LinkId=193059](http://go.microsoft.com/fwlink/p/?LinkId=193059).</span></span>  
  
- <span data-ttu-id="b505e-106">処理サーバーと管理クライアントのように、SQL Server とそのクライアントとの間で暗号化を有効にする方法については、「[透過的なデータ暗号化 (TDE)](https://msdn.microsoft.com/library/bb934049.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-106">For more information about how to enable encryption between SQL Server and its clients such as processing servers and administration clients, see [Transparent Data Encryption (TDE)](https://msdn.microsoft.com/library/bb934049.aspx).</span></span>  
  
- <span data-ttu-id="b505e-107">オンプレミス サーバーの ID 管理を構成する方法の詳細については、[Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-107">For more information about how to configure identity management for your on-premises servers, see [Identity Manager ](https://docs.microsoft.com/microsoft-identity-manager/).</span></span>  
  
  <span data-ttu-id="b505e-108">このセクションのトピック以外にも、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b505e-108">In addition to the topics in this section, you should review the following information:</span></span>  
  
- <span data-ttu-id="b505e-109">セキュリティで保護された展開の計画と管理に関する概念的な情報については、「[セキュリティの計画](../core/planning-for-security.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-109">For conceptual information about planning and maintaining a secure deployment, see [Planning for Security](../core/planning-for-security.md).</span></span>  
  
- <span data-ttu-id="b505e-110">管理者とシステム ユーザー用のアクセスを構成する方法については、「[BizTalk Server のセキュリティの管理](../core/managing-biztalk-server-security.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-110">For information about configuring access for administrators and system users, see [Managing BizTalk Server Security](../core/managing-biztalk-server-security.md).</span></span>  
  
- <span data-ttu-id="b505e-111">BizTalk Server のセキュリティ機能の詳細については、「[Secure and protect your BizTalk messages (BitTalk メッセージのセキュリティ確保と保護)](../core/secure-and-protect-your-biztalk-messages.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-111">For more information about security features in BizTalk Server, see [Secure and protect your BizTalk messages](../core/secure-and-protect-your-biztalk-messages.md).</span></span>  
  
- <span data-ttu-id="b505e-112">セキュリティで保護されたメッセージの実装方法については、「[メッセージ セキュリティの実装](../core/implementing-message-security.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-112">For more information about how to implement secure messages, see [Implementing Message Security](../core/implementing-message-security.md).</span></span>  
  
- <span data-ttu-id="b505e-113">BizTalk Server が使用する Windows グループおよびユーザー アカウントの詳細については、「[BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b505e-113">For more information about Windows groups and user accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="additional-configuration-topics"></a><span data-ttu-id="b505e-114">構成に関するその他のトピック</span><span class="sxs-lookup"><span data-stu-id="b505e-114">Additional Configuration Topics</span></span>  
 
 [<span data-ttu-id="b505e-115">BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="b505e-115">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
 [<span data-ttu-id="b505e-116">Azure VM での BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="b505e-116">Configuring BizTalk Server on an Azure VM</span></span>](http://msdn.microsoft.com/library/azure/jj248689.aspx)  
  
[<span data-ttu-id="b505e-117">BizTalk Server のクラスター構成</span><span class="sxs-lookup"><span data-stu-id="b505e-117">Configure BizTalk Server in a Cluster</span></span>](../install-and-config-guides/configure-biztalk-server-in-a-cluster.md)
    
  
## <a name="see-also"></a><span data-ttu-id="b505e-118">参照</span><span class="sxs-lookup"><span data-stu-id="b505e-118">See Also</span></span>  
 <span data-ttu-id="b505e-119">[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md) </span><span class="sxs-lookup"><span data-stu-id="b505e-119">[Access Control and Data Security](../core/access-control-and-data-security.md) </span></span>  
 <span data-ttu-id="b505e-120">[セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md) </span><span class="sxs-lookup"><span data-stu-id="b505e-120">[Minimum Security User Rights](../core/minimum-security-user-rights.md) </span></span>  
 <span data-ttu-id="b505e-121">[セキュリティの計画](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="b505e-121">[Planning for Security](../core/planning-for-security.md) </span></span>  
 [<span data-ttu-id="b505e-122">BizTalk Server のシステム アーキテクチャの設計</span><span class="sxs-lookup"><span data-stu-id="b505e-122">Designing the System Architectures for BizTalk Server</span></span>](../core/designing-the-system-architectures-for-biztalk-server.md)   
