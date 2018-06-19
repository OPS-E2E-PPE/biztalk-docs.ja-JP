---
title: セキュリティの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security
ms.assetid: 357ebf63-a35e-4ce4-a754-be880946f9fc
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5d327de93941278b9b1dcecc9378183c6a2f77a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22213978"
---
# <a name="security-summary"></a><span data-ttu-id="c1599-102">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="c1599-102">Security Summary</span></span>
## <a name="overview"></a><span data-ttu-id="c1599-103">概要</span><span class="sxs-lookup"><span data-stu-id="c1599-103">Overview</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="c1599-104">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT メッセージングとオートメーションの機能を提供する BizTalk アプリケーションを容易に開発およびランタイムのコンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1599-104"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides development and runtime components to facilitate BizTalk applications that provide SWIFT messaging and automation functionality.</span></span> <span data-ttu-id="c1599-105">使用して開発されたアプリケーション[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]BizTalk アプリケーションは、ネイティブで保護された[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および IIS と ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]セキュリティ機能です。</span><span class="sxs-lookup"><span data-stu-id="c1599-105">Applications developed by using [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] are BizTalk applications and are secured by native [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], and IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] security features.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c1599-106">事実上の通信の暗号化されたインターネット標準とプロトコルを使用してシステムの各要素のプライバシーを保護します。</span><span class="sxs-lookup"><span data-stu-id="c1599-106"> protects privacy of system elements by using de facto Internet encrypted communications standards and protocols.</span></span> <span data-ttu-id="c1599-107">通信参加者、プロセス、および情報が、署名証明書を使用して保護されます[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびエンタープライズ シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="c1599-107">Communication participants, processes, and information are secured by using signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c1599-108">などのメカニズムとリソース使用率の承認を強制も[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロールと[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびメッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="c1599-108"> also enforces authorization of resource usage with mechanisms such as [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and the MessageBox database.</span></span>  
  
 <span data-ttu-id="c1599-109">ネイティブに加えて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]を定義し、作成、修復、承認、およびビジネス ユーザーによって SWIFT メッセージの送信のセキュリティのセマンティクスを適用します。</span><span class="sxs-lookup"><span data-stu-id="c1599-109">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] defines and enforces security semantics for the creation, repair, approval, and submission of SWIFT messages by business users.</span></span> <span data-ttu-id="c1599-110">使用してこのユーザー レベルのセキュリティを強制[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]のデジタル署名してユーザー ワークステーション、および証明書とデータ整合性の検証で、テクノロジ[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]サーバー上のランタイム サービス。</span><span class="sxs-lookup"><span data-stu-id="c1599-110">This user-level security is enforced by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies on the user workstation, and certificate and data integrity verification by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] runtime services on the server.</span></span>  
  
 <span data-ttu-id="c1599-111">同時に、[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]設計、開発、および実行するシステムのセキュリティ保護 SWIFT メッセージングとワークフローの自動化のプラットフォーム、インフラストラクチャ、およびツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="c1599-111">Together, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="c1599-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="c1599-112">More information</span></span>  
 <span data-ttu-id="c1599-113">セキュリティのベスト プラクティスについては、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1599-113">For information about security best practices, see the following:</span></span>  
  
-   <span data-ttu-id="c1599-114">TechNet セキュリティ リソース センター:</span><span class="sxs-lookup"><span data-stu-id="c1599-114">TechNet Security Resource Center:</span></span>  
  
     [<span data-ttu-id="c1599-115">http://go.microsoft.com/fwlink/p/?LinkId=27741</span><span class="sxs-lookup"><span data-stu-id="c1599-115">http://go.microsoft.com/fwlink/p/?LinkId=27741</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

-   <span data-ttu-id="c1599-116">Symantec セキュリティ ガイド 』 で説明されているベスト プラクティスを実装する、ツールを使用する方法を示す[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]セキュリティ操作ガイドの「 [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c1599-116">Symantec security guide showing how to use their tools to implement the best practices described in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Security Operations Guide for [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span></span>  
  
     [<span data-ttu-id="c1599-117">http://go.microsoft.com/fwlink/p/?LinkId=28274</span><span class="sxs-lookup"><span data-stu-id="c1599-117">http://go.microsoft.com/fwlink/p/?LinkId=28274</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
-   <span data-ttu-id="c1599-118">については、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]セキュリティ通知サービス。</span><span class="sxs-lookup"><span data-stu-id="c1599-118">Information about the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Security Notification Service:</span></span>  
  
     [<span data-ttu-id="c1599-119">http://go.microsoft.com/fwlink/p/?LinkId=27744</span><span class="sxs-lookup"><span data-stu-id="c1599-119">http://go.microsoft.com/fwlink/p/?LinkId=27744</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a><span data-ttu-id="c1599-120">参照</span><span class="sxs-lookup"><span data-stu-id="c1599-120">See Also</span></span>  
[<span data-ttu-id="c1599-121">実行時、メッセージの修復、FIN 応答、およびメッセージング</span><span class="sxs-lookup"><span data-stu-id="c1599-121">Runtime, message repair, FIN response, and messaging</span></span>](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)