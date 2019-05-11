---
title: BizTalk Adapter for PeopleSoft Enterprise でのセキュリティ |Microsoft Docs
description: BizTalk で PeopleSoft Enterprise アダプターを使用するアプリケーションをセキュリティで保護するのにエンタープライズ シングル サインオン (SSO) を使用します。
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cfdf0db-6f83-4322-a57a-e373c7245700
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 744eb0991f92a1517e7b5abfb77acfe77b73140b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279934"
---
# <a name="security-in-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="81385-103">BizTalk Adapter for PeopleSoft Enterprise でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="81385-103">Security in BizTalk Adapter for PeopleSoft Enterprise</span></span>

## <a name="overview"></a><span data-ttu-id="81385-104">概要</span><span class="sxs-lookup"><span data-stu-id="81385-104">Overview</span></span>
<span data-ttu-id="81385-105">Microsoft BizTalk Adapter for PeopleSoft Enterprise は、シングル サインオン (SSO) サポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="81385-105">Microsoft BizTalk Adapter for PeopleSoft Enterprise provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="81385-106">エンタープライズ シングル サインオン ツールによって作成される関連アプリケーションは、PeopleSoft などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="81385-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as PeopleSoft.</span></span> 

<span data-ttu-id="81385-107">このセクションでは、PeopleSoft Enterprise のセキュリティで保護された環境で Microsoft BizTalk Server アダプターを展開するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="81385-107">This section provides guidelines for deploying Microsoft BizTalk Server Adapter for PeopleSoft Enterprise in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="81385-108">承認されたユーザーだけでは、BizTalk adapter for PeopleSoft Enterprise の使用を制限することをお勧めします。 クライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="81385-108">We recommended that you restrict the use of BizTalk Adapter for PeopleSoft Enterprise to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="81385-109">次のステップ</span><span class="sxs-lookup"><span data-stu-id="81385-109">Next steps</span></span> 
  
-   [<span data-ttu-id="81385-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="81385-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on2.md)  
  
-   [<span data-ttu-id="81385-111">シングル サインオンと BizTalk Adapter for PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="81385-111">Single Sign-On and BizTalk Adapter for PeopleSoft Enterprise</span></span>](../core/single-sign-on-and-biztalk-adapter-for-peoplesoft-enterprise.md)  
  
-   [<span data-ttu-id="81385-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="81385-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications2.md)  
  
-   [<span data-ttu-id="81385-113">ポートの作成</span><span class="sxs-lookup"><span data-stu-id="81385-113">Creating Ports</span></span>](../core/creating-ports.md)  
  
-   [<span data-ttu-id="81385-114">仮想ディレクトリを構成する方法</span><span class="sxs-lookup"><span data-stu-id="81385-114">How to Configure the Virtual Directory</span></span>](../core/how-to-configure-the-virtual-directory.md)  
  
-   [<span data-ttu-id="81385-115">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="81385-115">How to Configure the HTTP Receive Adapter</span></span>](../core/how-to-configure-the-http-receive-adapter1.md)  
  
-   [<span data-ttu-id="81385-116">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="81385-116">Running Orchestrations</span></span>](../core/running-orchestrations2.md)  
  
-   [<span data-ttu-id="81385-117">SSO プロジェクトの実行</span><span class="sxs-lookup"><span data-stu-id="81385-117">Running SSO Projects</span></span>](../core/running-sso-projects1.md)