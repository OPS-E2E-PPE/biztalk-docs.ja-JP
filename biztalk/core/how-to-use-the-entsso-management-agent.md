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
ms.openlocfilehash: e5316fc279ea7dc0c29038ffefb1b16770bf6469
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383347"
---
# <a name="how-to-use-the-entsso-management-agent"></a><span data-ttu-id="22b56-102">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="22b56-102">How to Use the ENTSSO Management Agent</span></span>
<span data-ttu-id="22b56-103">このバージョン エンタープライズ シングル サインオン (SSO) にはには、管理エージェント (MA) の Microsoft Identity Integration Server (MIIS)、エンタープライズ SSO を MIIS のアカウント同期機能の使用と統合が含まれています。</span><span class="sxs-lookup"><span data-stu-id="22b56-103">This version of Enterprise Single Sign-On (SSO) contains a Management Agent (MA) for Microsoft Identity Integration Server (MIIS), which integrates Enterprise SSO with the account synchronization capabilities of MIIS.</span></span> <span data-ttu-id="22b56-104">これにより、MIIS 管理者、SSO データベースで SSO マッピングを管理できます。</span><span class="sxs-lookup"><span data-stu-id="22b56-104">This enables an MIIS administrator to manage SSO mappings in the SSO Database.</span></span>  
  
 <span data-ttu-id="22b56-105">Windows ドメイン アカウント間で、エンタープライズ SSO でマッピングの作成 (*domainname \username*) および外部資格情報。</span><span class="sxs-lookup"><span data-stu-id="22b56-105">In Enterprise SSO, mappings are created between Windows Domain accounts (*domainname\username*) and external credentials.</span></span> <span data-ttu-id="22b56-106">外部データ ソースの Active Directory 管理エージェントと管理エージェントがある場合 (例。RACF MA)、SSO データベース内のマッピングを管理、エンタープライズ SSO MA (ENTSSO MA) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="22b56-106">If you have an Active Directory Management Agent, and the Management Agent for the external Data Source (example: RACF MA), you can use the Enterprise SSO MA (ENTSSO MA) to manage mappings in the SSO Database.</span></span> <span data-ttu-id="22b56-107">ENTSSO MA は、*呼び出しベースのエクスポート*管理エージェントのみです。</span><span class="sxs-lookup"><span data-stu-id="22b56-107">ENTSSO MA is a *Call-Based Export* Management Agent only.</span></span>  
  
 <span data-ttu-id="22b56-108">管理エージェントを構成するには次の 3 つの別々 の部分に。</span><span class="sxs-lookup"><span data-stu-id="22b56-108">You configure the Management Agent in three separate parts:</span></span>  
  
- <span data-ttu-id="22b56-109">構成ファイル (ENTSSO.xml)</span><span class="sxs-lookup"><span data-stu-id="22b56-109">A configuration file (ENTSSO.xml)</span></span>  
  
- <span data-ttu-id="22b56-110">MIIS ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22b56-110">The MIIS user interface</span></span>  
  
- <span data-ttu-id="22b56-111">ENTSSO ユーザー インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22b56-111">The ENTSSO user interface</span></span>  
  
  <span data-ttu-id="22b56-112">このセクションのトピックでは、構成プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="22b56-112">The topics in this section describe the configuration process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22b56-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="22b56-113">In This Section</span></span>  
  
-   [<span data-ttu-id="22b56-114">XML ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="22b56-114">Configuring the XML File</span></span>](../core/configuring-the-xml-file.md)  
  
-   [<span data-ttu-id="22b56-115">ENTSSO MA 用に MIIS を構成する方法</span><span class="sxs-lookup"><span data-stu-id="22b56-115">How to Configure MIIS for ENTSSO MA</span></span>](../core/how-to-configure-miis-for-entsso-ma.md)  
  
-   [<span data-ttu-id="22b56-116">MIIS パスワード同期用に ENTSSO を構成する方法</span><span class="sxs-lookup"><span data-stu-id="22b56-116">How to Configure ENTSSO for MIIS Password Sync</span></span>](../core/how-to-configure-entsso-for-miis-password-sync.md)