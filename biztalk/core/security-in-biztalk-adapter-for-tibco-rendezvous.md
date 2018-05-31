---
title: TIBCO Rendezvous アダプターのセキュリティ |Microsoft ドキュメント
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
ms.openlocfilehash: 0c06b241bff7595f4119a0226a07d45d365a4faa
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015833"
---
# <a name="sso-security-in-biztalk-adapter-for-tibco-rendezvous"></a><span data-ttu-id="421bb-103">BizTalk Adapter for TIBCO Rendezvous での SSO のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="421bb-103">SSO Security in BizTalk Adapter for TIBCO Rendezvous</span></span>

## <a name="overview"></a><span data-ttu-id="421bb-104">概要</span><span class="sxs-lookup"><span data-stu-id="421bb-104">Overview</span></span>
<span data-ttu-id="421bb-105">Microsoft BizTalk Adapter for TIBCO Rendezvous ではシングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="421bb-105">Microsoft BizTalk Adapter for TIBCO Rendezvous provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="421bb-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、TIBCO Rendezvous などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="421bb-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as TIBCO Rendezvous.</span></span> 
  
> [!CAUTION]
>  <span data-ttu-id="421bb-107">クライアントのファイルは基幹業務 (LOB) アプリケーションに直接接続されるので、エンタープライズ アプリケーション用の BizTalk Adapter の使用は許可されたユーザーだけに制限することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="421bb-107">It is highly recommended that you restrict the use of BizTalk Adapter for Enterprise Applications to authorized users only, because the client files directly connect to the line-of-business applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="421bb-108">次の手順</span><span class="sxs-lookup"><span data-stu-id="421bb-108">Next steps</span></span>
  
-   [<span data-ttu-id="421bb-109">SSO の要件</span><span class="sxs-lookup"><span data-stu-id="421bb-109">SSO Requirements</span></span>](../core/requirements-for-single-sign-on3.md)  
  
-   [<span data-ttu-id="421bb-110">SSO とアダプター</span><span class="sxs-lookup"><span data-stu-id="421bb-110">SSO and the adapter</span></span>](../core/single-sign-on-and-biztalk-adapter-for-tibco-rendezvous.md)  
  
-   [<span data-ttu-id="421bb-111">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="421bb-111">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications1.md)  
  
-   [<span data-ttu-id="421bb-112">送信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="421bb-112">Creating Send Ports</span></span>](../core/creating-send-ports2.md)