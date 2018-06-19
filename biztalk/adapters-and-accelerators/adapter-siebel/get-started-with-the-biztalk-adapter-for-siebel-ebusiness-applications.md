---
title: BizTalk Adapter for Siebel eBusiness Applications の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
ms.assetid: 0867f95f-977f-48bf-8c46-70fd6e4df56b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba067d0479bbcdae6d04c3affdcb9ee60e564cc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222058"
---
# <a name="get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="f3cb9-102">BizTalk Adapter for Siebel eBusiness Applications の概要します。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-102">Get started with the BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="f3cb9-103">このセクションでは、Microsoft に新しいユーザーのアダプター、前提条件、およびトピックの概要を説明する[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="f3cb9-104">機能についても説明[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]とアダプターを使用して、Siebel システムで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-104">It discusses the features of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the different operations that can be performed on the Siebel system using the adapter.</span></span>  
  
 <span data-ttu-id="f3cb9-105">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-105">What is an adapter?</span></span> <span data-ttu-id="f3cb9-106">アダプターは、ソフトウェア コンポーネントと基幹業務 (LOB) システムからメッセージを送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="f3cb9-107">アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を容易にです。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="f3cb9-108">各ビジネス システムは、特定のドキュメント形式およびプロトコルに従うことがあります、ために、アダプターは、共通に認識される標準とプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="f3cb9-109">アダプターは、2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-109">The adapters can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="f3cb9-110">**LOB アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-110">**LOB adapters**.</span></span> <span data-ttu-id="f3cb9-111">このようなアダプターが LOB システムへのアクセスをサービス指向のプログラミング モデルを提供、SAP の Siebel アダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="f3cb9-112">**データ アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-112">**Data adapters**.</span></span> <span data-ttu-id="f3cb9-113">このようなアダプターがデータベースにアクセスできるサービス指向のプログラミング モデルを提供、Oracle データベースまたは SQL Server 用のアダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="f3cb9-114">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f3cb9-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="f3cb9-115">(、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="f3cb9-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="f3cb9-116">(、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="f3cb9-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="f3cb9-117">(、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="f3cb9-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="f3cb9-118">(、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="f3cb9-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="f3cb9-119">(、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="f3cb9-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f3cb9-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="f3cb9-121">かどうかは既に分かっていなければを使用する方法、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]で、社内をお勧めする機能を表示することによって起動してで説明されているアダプターの機能[概要の BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span><span class="sxs-lookup"><span data-stu-id="f3cb9-121">If you do not already know how you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Overview of BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3cb9-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f3cb9-122">In This Section</span></span>  
  
-   [<span data-ttu-id="f3cb9-123">Siebel eBusiness Applications の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="f3cb9-123">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md) 
  
-   [<span data-ttu-id="f3cb9-124">Siebel アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="f3cb9-124">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)  
  
-   [<span data-ttu-id="f3cb9-125">コミュニティ リソース</span><span class="sxs-lookup"><span data-stu-id="f3cb9-125">Community Resources</span></span>](http://msdn.microsoft.com/library/ff5ec978-8cdd-418a-a25e-fd3746b64d8b)  
  
-   [<span data-ttu-id="f3cb9-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="f3cb9-126">Frequently Asked Questions</span></span>](http://msdn.microsoft.com/library/66953c15-08c5-48ac-a4ff-a72a82174f15)