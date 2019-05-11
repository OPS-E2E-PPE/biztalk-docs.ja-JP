---
title: TIBCO Rendezvous アダプターのセキュリティ |Microsoft Docs
description: Biztalk TIBCO Rendezvous アダプターを使用するアプリケーションをセキュリティで保護するのにエンタープライズ シングル サインオン (SSO) を使用します。
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec9011a8-43c3-4a6e-8c89-851c04ef4a1e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd96118e2d7301169b7fa3dd7c6fadf500feacf4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279778"
---
# <a name="sso-security-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="31015-103">BizTalk Adapter for TIBCO Rendezvous での SSO のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="31015-103">SSO Security in BizTalk Adapter for TIBCO Rendezvous</span></span>

## <a name="overview"></a><span data-ttu-id="31015-104">概要</span><span class="sxs-lookup"><span data-stu-id="31015-104">Overview</span></span>
<span data-ttu-id="31015-105">Microsoft BizTalk Adapter for TIBCO Rendezvous は、シングル サインオン (SSO) サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="31015-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="31015-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO Rendezvous などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="31015-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO Rendezvous.</span></span> 
  
> [!CAUTION]
>  <span data-ttu-id="31015-107">クライアント ファイルが基幹業務アプリケーションに直接接続できないため、承認されたユーザーだけに、エンタープライズ アプリケーション用 BizTalk アダプターの使用を制限することが強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31015-107">It is highly recommended that you restrict the use of BizTalk Adapter for Enterprise Applications to authorized users only, because the client files directly connect to the line-of-business applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31015-108">次のステップ</span><span class="sxs-lookup"><span data-stu-id="31015-108">Next steps</span></span>
  
-   [<span data-ttu-id="31015-109">SSO の要件</span><span class="sxs-lookup"><span data-stu-id="31015-109">SSO Requirements</span></span>](../core/requirements-for-single-sign-on3.md)  
  
-   [<span data-ttu-id="31015-110">SSO とアダプター</span><span class="sxs-lookup"><span data-stu-id="31015-110">SSO and the adapter</span></span>](../core/single-sign-on-and-biztalk-adapter-for-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="31015-111">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="31015-111">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications1.md)  
  
-   [<span data-ttu-id="31015-112">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="31015-112">Creating Send Ports</span></span>](../core/creating-send-ports2.md)