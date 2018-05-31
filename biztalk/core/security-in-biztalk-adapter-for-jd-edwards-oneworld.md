---
title: SSO を使用して JD Edwards OneWorld を保護する |Microsoft ドキュメント
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
ms.openlocfilehash: 97e72ffbc38cad2f5bbd622ed497663cf8ac5f3c
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015947"
---
# <a name="security-in-jd-edwards-oneworld"></a><span data-ttu-id="53aa5-103">JD Edwards OneWorld のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="53aa5-103">Security in JD Edwards OneWorld</span></span>

## <a name="overview"></a><span data-ttu-id="53aa5-104">概要</span><span class="sxs-lookup"><span data-stu-id="53aa5-104">Overview</span></span>
<span data-ttu-id="53aa5-105">Microsoft BizTalk Adapter for JD Edwards OneWorld ではシングル サインオン (SSO) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="53aa5-105">Microsoft BizTalk Adapter for JD Edwards OneWorld provides Single Sign-On (SSO) support.</span></span> <span data-ttu-id="53aa5-106">エンタープライズ シングル サインオン ツールで作成された関連アプリケーションは JD Edwards OneWorld などのサーバー システムを表します。</span><span class="sxs-lookup"><span data-stu-id="53aa5-106">An affiliate application created by Enterprise Single Sign-On tools represents a server system such as JD Edwards OneWorld.</span></span>  

<span data-ttu-id="53aa5-107">このセクションでは、セキュリティで保護された環境で Microsoft BizTalk Adapter for JD Edwards OneWorld を展開するためのガイドラインを示します。</span><span class="sxs-lookup"><span data-stu-id="53aa5-107">This section provides guidelines about how to deploy Microsoft BizTalk Adapter for JD Edwards OneWorld in a secure environment.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="53aa5-108">承認されたユーザーだけに、BizTalk adapter for JD Edwards OneWorld の使用を制限することをお勧めように、クライアント ファイルが基幹業務アプリケーションに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="53aa5-108">We recommended that you restrict the use of BizTalk Adapter for JD Edwards OneWorld to authorized users only, as the client files directly connect to the line-of-business applications.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="53aa5-109">次の手順</span><span class="sxs-lookup"><span data-stu-id="53aa5-109">Next steps</span></span>
  
-   [<span data-ttu-id="53aa5-110">シングル サインオンの要件</span><span class="sxs-lookup"><span data-stu-id="53aa5-110">Requirements for Single Sign-On</span></span>](../core/requirements-for-single-sign-on5.md)  
  
-   [<span data-ttu-id="53aa5-111">シングル サインオンと BizTalk Adapter for JD Enterprise OneWorld</span><span class="sxs-lookup"><span data-stu-id="53aa5-111">Single Sign-On and BizTalk Adapter for JD Enterprise OneWorld</span></span>](../core/single-sign-on-and-biztalk-adapter-for-jd-enterprise-oneworld.md)  
  
-   [<span data-ttu-id="53aa5-112">関連アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="53aa5-112">Creating Affiliate Applications</span></span>](../core/creating-affiliate-applications3.md)  
  
-   [<span data-ttu-id="53aa5-113">仮想ディレクトリの構成</span><span class="sxs-lookup"><span data-stu-id="53aa5-113">Configuring the Virtual Directory</span></span>](../core/configuring-the-virtual-directory.md)  
  
-   [<span data-ttu-id="53aa5-114">HTTP 受信アダプターを構成する方法</span><span class="sxs-lookup"><span data-stu-id="53aa5-114">How to Configure the HTTP Receive Adapter</span></span>](../core/how-to-configure-the-http-receive-adapter2.md)  
  
-   [<span data-ttu-id="53aa5-115">送信ポートと受信ポートの作成</span><span class="sxs-lookup"><span data-stu-id="53aa5-115">Creating Send and Receive Ports</span></span>](../core/creating-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="53aa5-116">BizTalk Server プロジェクトへのスキーマのインポート</span><span class="sxs-lookup"><span data-stu-id="53aa5-116">Importing Schemas into BizTalk Server Projects</span></span>](../core/importing-schemas-into-biztalk-server-projects1.md)  
  
-   [<span data-ttu-id="53aa5-117">オーケストレーションの実行</span><span class="sxs-lookup"><span data-stu-id="53aa5-117">Running Orchestrations</span></span>](../core/running-orchestrations1.md)  
  
-   [<span data-ttu-id="53aa5-118">SSO プロジェクトの実行</span><span class="sxs-lookup"><span data-stu-id="53aa5-118">Running SSO Projects</span></span>](../core/running-sso-projects3.md)