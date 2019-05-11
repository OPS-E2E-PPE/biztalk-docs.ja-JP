---
title: SSO を使用して、TIBCO EMS をセキュリティで保護する |Microsoft Docs
description: Microsoft BizTalk アダプターを BizTalk Server で TIBCO Enterprise Message Service を使用する場合のセキュリティの概要
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0eccb44b-e9d8-42c2-a575-47f1d1cfe93c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec373526a8e436b21614acab22cb9d2120936f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280289"
---
# <a name="security-in-biztalk-adapter-for-tibco-ems"></a><span data-ttu-id="bd77d-103">BizTalk Adapter for TIBCO EMS のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="bd77d-103">Security in BizTalk Adapter for TIBCO EMS</span></span>

## <a name="overview"></a><span data-ttu-id="bd77d-104">概要</span><span class="sxs-lookup"><span data-stu-id="bd77d-104">Overview</span></span>
<span data-ttu-id="bd77d-105">Microsoft の BizTalk Adapter for TIBCO Enterprise Message Service は、シングル サインオン (SSO) サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd77d-105">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="bd77d-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO Enterprise Message Service などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="bd77d-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO Enterprise Message Service.</span></span>  

<span data-ttu-id="bd77d-107">このセクションでは、BizTalk Adapter for TIBCO Enterprise Message Service セキュリティで保護された環境に展開する方法のガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd77d-107">This section provides guidelines on how to deploy BizTalk Adapter for TIBCO Enterprise Message Service in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bd77d-108">承認されたユーザーだけに、BizTalk Adapter for Enterprise Message Service の使用を制限することを強くお勧めクライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="bd77d-108">It is highly recommended that you restrict the use of BizTalk Adapter for Enterprise Message Service to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>    

  
## <a name="next-steps"></a><span data-ttu-id="bd77d-109">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bd77d-109">Next steps</span></span>
  
-   [<span data-ttu-id="bd77d-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="bd77d-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on4.md)  
  
-   [<span data-ttu-id="bd77d-111">シングル サインオンおよび BizTalk Adapter for TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="bd77d-111">Single Sign-On and BizTalk Adapter for TIBCO Enterprise Message Service</span></span>](../core/single-sign-on-and-biztalk-adapter-for-tibco-enterprise-message-service.md)  
  
-   [<span data-ttu-id="bd77d-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="bd77d-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications5.md)  
  
-   [<span data-ttu-id="bd77d-113">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="bd77d-113">Creating Send Ports</span></span>](../core/creating-send-ports1.md)  
  
-   [<span data-ttu-id="bd77d-114">SSO プロジェクトの実行</span><span class="sxs-lookup"><span data-stu-id="bd77d-114">Running SSO Projects</span></span>](../core/running-sso-projects2.md)