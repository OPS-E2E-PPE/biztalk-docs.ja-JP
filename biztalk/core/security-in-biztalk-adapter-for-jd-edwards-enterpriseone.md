---
title: SSO を使用して、JD Edwards EnterpriseOne をセキュリティで保護する |Microsoft Docs
description: Microsoft BizTalk Adapter JD Edwards EnterpriseOne を BizTalk Server で使用する場合のセキュリティの概要
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24c9802e-485d-4632-bc27-3285f35d34e3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c3ba61cf40d691b1ee589fb850c8f3d5aa4a755
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279968"
---
# <a name="security-in-jd-edwards-enterpriseone"></a><span data-ttu-id="e9a4a-103">JD Edwards EnterpriseOne のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="e9a4a-103">Security in JD Edwards EnterpriseOne</span></span>

## <a name="overview"></a><span data-ttu-id="e9a4a-104">概要</span><span class="sxs-lookup"><span data-stu-id="e9a4a-104">Overview</span></span>

<span data-ttu-id="e9a4a-105">Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、シングル サインオン (SSO) サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e9a4a-105">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="e9a4a-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、JD Edwards EnterpriseOne などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="e9a4a-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as JD Edwards EnterpriseOne.</span></span> 

<span data-ttu-id="e9a4a-107">このセクションでは、JD Edwards EnterpriseOne のセキュリティで保護された環境で Microsoft BizTalk Server アダプターを展開するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="e9a4a-107">This section provides guidelines for deploying Microsoft BizTalk Server Adapter for JD Edwards EnterpriseOne in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e9a4a-108">承認されたユーザーだけでは、BizTalk Adapter for JD Edwards EnterpriseOne の使用を制限することをお勧めします。 クライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="e9a4a-108">We recommended that you restrict the use of BizTalk Adapter for JD Edwards EnterpriseOne to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e9a4a-109">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e9a4a-109">Next steps</span></span> 
  
-   [<span data-ttu-id="e9a4a-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="e9a4a-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on1.md)  
  
-   [<span data-ttu-id="e9a4a-111">シングル サインオンと BizTalk Adapter for JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="e9a4a-111">Single Sign-On and BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/single-sign-on-and-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
  
-   [<span data-ttu-id="e9a4a-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="e9a4a-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications4.md)  
  
-   [<span data-ttu-id="e9a4a-113">送信ポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e9a4a-113">How to Create a Send Port</span></span>](../core/how-to-create-a-send-port1.md)