---
title: "ENTSSO 管理エージェントを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c0f7d2c04a2707cf965f64ff7a559d8642a12c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="2cb20-102">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="2cb20-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="2cb20-103">エンタープライズ シングル サインオン (SSO) のこのバージョンには、Microsoft Identity Integration Server (MIIS) の管理エージェントが含まれます。この管理エージェントは、エンタープライズ SSO を MIIS のアカウント同期機能と統合します。</span><span class="sxs-lookup"><span data-stu-id="2cb20-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="2cb20-104">これにより、MIIS 管理者は、SSO データベースで SSO マッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2cb20-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="2cb20-105">エンタープライズ SSO でマッピングは Windows ドメインのアカウント間で作成されます (*domainname \username*) および外部資格情報。</span><span class="sxs-lookup"><span data-stu-id="2cb20-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="2cb20-106">Active Directory 管理エージェント、および外部データ ソースの管理エージェント (例: RACF MA) がある場合は、エンタープライズ SSO MA (ENTSSO MA) を使用して、SSO データベースでのマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2cb20-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="2cb20-107">ENTSSO MA は、*呼び出しベースのエクスポート*管理エージェントのみです。</span><span class="sxs-lookup"><span data-stu-id="2cb20-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="2cb20-108">管理エージェントは、次の 3 つの異なる部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2cb20-108">You configure the Management Agent in three separate parts:</span></span>  
  
-   <span data-ttu-id="2cb20-109">構成ファイル (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="2cb20-109">A configuration file (ENTSSO.xml)</span></span>  
  
-   <span data-ttu-id="2cb20-110">MIIS ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cb20-110">The MIIS user interface</span></span>  
  
-   <span data-ttu-id="2cb20-111">ENTSSO ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2cb20-111">The ENTSSO user interface</span></span>  
  
 <span data-ttu-id="2cb20-112">ここでは、構成プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2cb20-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cb20-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2cb20-113">In This Section</span></span>  
  
-   [<span data-ttu-id="2cb20-114">XML ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2cb20-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="2cb20-115">ENTSSO MA 用に MIIS を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2cb20-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="2cb20-116">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2cb20-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)