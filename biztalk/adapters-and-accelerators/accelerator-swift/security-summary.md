---
title: セキュリティの概要 |Microsoft Docs
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
ms.openlocfilehash: df0062eca25e95c41c07d2e8dbf9ccac0a4694a3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995355"
---
# <a name="security-summary"></a><span data-ttu-id="6086c-102">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="6086c-102">Security Summary</span></span>
## <a name="overview"></a><span data-ttu-id="6086c-103">概要</span><span class="sxs-lookup"><span data-stu-id="6086c-103">Overview</span></span>
<span data-ttu-id="6086c-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] SWIFT のメッセージングと自動化機能を提供する BizTalk アプリケーションを容易に開発およびランタイムのコンポーネントを提供します。</span><span class="sxs-lookup"><span data-stu-id="6086c-104">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides development and runtime components to facilitate BizTalk applications that provide SWIFT messaging and automation functionality.</span></span> <span data-ttu-id="6086c-105">使用して開発されたアプリケーション[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]BizTalk アプリケーションは、ネイティブで保護されている[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]、 [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]、 [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]、および IIS と ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]セキュリティ機能。</span><span class="sxs-lookup"><span data-stu-id="6086c-105">Applications developed by using [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] are BizTalk applications and are secured by native [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)], [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)], and IIS/ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] security features.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6086c-106"> 業界標準の暗号化されたインターネット通信の規格とプロトコルを使用してシステムの各要素のプライバシーを保護します。</span><span class="sxs-lookup"><span data-stu-id="6086c-106"> protects privacy of system elements by using de facto Internet encrypted communications standards and protocols.</span></span> <span data-ttu-id="6086c-107">署名の証明書を使用して、通信参加者、プロセス、および情報が保護されます[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびエンタープライズ シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="6086c-107">Communication participants, processes, and information are secured by using signing certificates, [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and Enterprise Single Sign-On.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6086c-108"> メカニズムとリソース使用量の承認をなども強制[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]ロールと[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]認証、およびメッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="6086c-108"> also enforces authorization of resource usage with mechanisms such as [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] Roles and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Authentication, and the MessageBox database.</span></span>  
  
 <span data-ttu-id="6086c-109">ネイティブに加えて[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]セキュリティ機能、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]を定義および作成、修復、承認、およびビジネス ユーザーが SWIFT メッセージの送信のセキュリティのセマンティクスを適用します。</span><span class="sxs-lookup"><span data-stu-id="6086c-109">In addition to native [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] security features, [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] defines and enforces security semantics for the creation, repair, approval, and submission of SWIFT messages by business users.</span></span> <span data-ttu-id="6086c-110">使用してこのユーザー レベルのセキュリティが適用される[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]デジタル署名してユーザー ワークステーション、および証明書とデータ整合性の検証でテクノロジ[!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)]サーバー上のランタイム サービス。</span><span class="sxs-lookup"><span data-stu-id="6086c-110">This user-level security is enforced by using [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] digital signing technologies on the user workstation, and certificate and data integrity verification by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev_md](../../includes/a4swift-currentversion-abbrev-md.md)] runtime services on the server.</span></span>  
  
 <span data-ttu-id="6086c-111">同時に、[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]と[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]設計、開発、および実行するセキュリティ保護された SWIFT メッセージングとワークフロー オートメーション システムのプラットフォーム、インフラストラクチャ、およびツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="6086c-111">Together, [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provide the platform, infrastructure, and tools for designing, developing, and executing secure SWIFT messaging and workflow automation systems.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="6086c-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6086c-112">More information</span></span>  
 <span data-ttu-id="6086c-113">セキュリティのベスト プラクティスについては、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6086c-113">For information about security best practices, see the following:</span></span>  
  
- <span data-ttu-id="6086c-114">TechNet セキュリティ リソース センター:</span><span class="sxs-lookup"><span data-stu-id="6086c-114">TechNet Security Resource Center:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27741](http://go.microsoft.com/fwlink/p/?LinkId=27741)  
  

- <span data-ttu-id="6086c-115">Symantec のセキュリティ ガイド、ツールを使用して、Microsoft のセキュリティ操作ガイドで説明されているベスト プラクティスを実装する方法を示す[!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6086c-115">Symantec security guide showing how to use their tools to implement the best practices described in Microsoft Security Operations Guide for [!INCLUDE[btsWin2kSvr](../../includes/btswin2ksvr-md.md)]:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=28274](http://go.microsoft.com/fwlink/p/?LinkId=28274)  

  
- <span data-ttu-id="6086c-116">Microsoft Security Notification Service に関する情報:</span><span class="sxs-lookup"><span data-stu-id="6086c-116">Information about the Microsoft Security Notification Service:</span></span>  
  
   [http://go.microsoft.com/fwlink/p/?LinkId=27744](http://go.microsoft.com/fwlink/p/?LinkId=27744)  
  
  
## <a name="see-also"></a><span data-ttu-id="6086c-117">参照</span><span class="sxs-lookup"><span data-stu-id="6086c-117">See Also</span></span>  
[<span data-ttu-id="6086c-118">ランタイム、メッセージの修復、FIN 応答、メッセージング</span><span class="sxs-lookup"><span data-stu-id="6086c-118">Runtime, message repair, FIN response, and messaging</span></span>](../../adapters-and-accelerators/accelerator-swift/runtime-message-repair-fin-response-and-messaging.md)