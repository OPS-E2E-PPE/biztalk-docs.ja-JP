---
title: ENTSSO 管理エージェントを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9c89b494-db12-4d2a-a030-6acd34489cab
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68c354f2250e9abc6a02ea52f4b7c106f57144e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018478"
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="291ed-102">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="291ed-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="291ed-103">エンタープライズ シングル サインオン (SSO) のこのバージョンには、Microsoft Identity Integration Server (MIIS) の管理エージェントが含まれます。この管理エージェントは、エンタープライズ SSO を MIIS のアカウント同期機能と統合します。</span><span class="sxs-lookup"><span data-stu-id="291ed-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="291ed-104">これにより、MIIS 管理者は、SSO データベースで SSO マッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="291ed-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="291ed-105">Windows ドメイン アカウント間で、エンタープライズ SSO でマッピングの作成 (*domainname \username*) および外部資格情報。</span><span class="sxs-lookup"><span data-stu-id="291ed-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="291ed-106">Active Directory 管理エージェント、および外部データ ソースの管理エージェント (例: RACF MA) がある場合は、エンタープライズ SSO MA (ENTSSO MA) を使用して、SSO データベースでのマッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="291ed-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="291ed-107">ENTSSO MA は、*呼び出しベースのエクスポート*管理エージェントのみです。</span><span class="sxs-lookup"><span data-stu-id="291ed-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="291ed-108">管理エージェントは、次の 3 つの異なる部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="291ed-108">You configure the Management Agent in three separate parts:</span></span>  
  
- <span data-ttu-id="291ed-109">構成ファイル (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="291ed-109">A configuration file (ENTSSO.xml)</span></span>  
  
- <span data-ttu-id="291ed-110">MIIS ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="291ed-110">The MIIS user interface</span></span>  
  
- <span data-ttu-id="291ed-111">ENTSSO ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="291ed-111">The ENTSSO user interface</span></span>  
  
  <span data-ttu-id="291ed-112">ここでは、構成プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="291ed-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="291ed-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="291ed-113">In This Section</span></span>  
  
-   [<span data-ttu-id="291ed-114">XML ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="291ed-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="291ed-115">ENTSSO MA 用に MIIS を構成する方法</span><span class="sxs-lookup"><span data-stu-id="291ed-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="291ed-116">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="291ed-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)