---
title: SSO を使用して、JD Edwards OneWorld をセキュリティで保護する |Microsoft Docs
description: Microsoft BizTalk Adapter JD Edwards OneWorld を BizTalk Server で使用する場合のセキュリティの概要
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: beb736a8-d95f-4d44-a882-2d437c4892f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b44e203a614edf4fdf6fe1decd5862c5c33d3430
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279965"
---
# <a name="security-in-jd-edwards-oneworld"></a><span data-ttu-id="4d049-103">JD Edwards OneWorld のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="4d049-103">Security in JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="4d049-104">概要</span><span class="sxs-lookup"><span data-stu-id="4d049-104">Overview</span></span>
<span data-ttu-id="4d049-105">Microsoft の BizTalk Adapter for JD Edwards OneWorld は、シングル サインオン (SSO) サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d049-105">Microsoft BizTalk Adapter for JD Edwards OneWorld provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="4d049-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、JD Edwards OneWorld などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="4d049-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as JD Edwards OneWorld.</span></span>  

<span data-ttu-id="4d049-107">このセクションでは、Microsoft BizTalk Adapter for JD Edwards OneWorld のセキュリティで保護された環境に展開する方法についてのガイドラインを提供します。</span><span class="sxs-lookup"><span data-stu-id="4d049-107">This section provides guidelines about how to deploy Microsoft BizTalk Adapter for JD Edwards OneWorld in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="4d049-108">承認されたユーザーだけでは、BizTalk Adapter for JD Edwards OneWorld の使用を制限することをお勧めします。 クライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="4d049-108">We recommended that you restrict the use of BizTalk Adapter for JD Edwards OneWorld to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="4d049-109">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4d049-109">Next steps</span></span>
  
-   [<span data-ttu-id="4d049-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="4d049-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on5.md)  
  
-   [<span data-ttu-id="4d049-111">シングル サインオンと BizTalk Adapter for JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="4d049-111">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>](../core/single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld.md)  
  
-   [<span data-ttu-id="4d049-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="4d049-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications3.md)  
  
-   [<span data-ttu-id="4d049-113">仮想ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="4d049-113">Configuring the Virtual Directory</span></span>](../core/configuring-the-virtual-directory.md)  
  
-   [<span data-ttu-id="4d049-114">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="4d049-114">How to Configure the HTTP Receive Adapter</span></span>](../core/how-to-configure-the-http-receive-adapter2.md)  
  
-   [<span data-ttu-id="4d049-115">送信ポートと受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="4d049-115">Creating Send and Receive Ports</span></span>](../core/creating-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="4d049-116">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="4d049-116">Importing Schemas into BizTalk Server Projects</span></span>](../core/importing-schemas-into-biztalk-server-projects1.md)  
  
-   [<span data-ttu-id="4d049-117">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="4d049-117">Running Orchestrations</span></span>](../core/running-orchestrations1.md)  
  
-   [<span data-ttu-id="4d049-118">SSO プロジェクトの実行</span><span class="sxs-lookup"><span data-stu-id="4d049-118">Running SSO Projects</span></span>](../core/running-sso-projects3.md)