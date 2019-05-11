---
title: SQL 用 BizTalk アダプターの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53a5021825d7e707b0f7f63935145986252ddc32
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369409"
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a><span data-ttu-id="b993f-102">SQL 用 BizTalk アダプターを概要します。</span><span class="sxs-lookup"><span data-stu-id="b993f-102">Get started with the BizTalk adapter for SQL</span></span>

  
 <span data-ttu-id="b993f-103">このセクションでは、ユーザーが Microsoft に新しいアダプター、前提条件、およびトピックの概要を示します[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="b993f-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b993f-104">機能について説明します[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]と、アダプターを使用して SQL Server データベースで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="b993f-104">It discusses the features of [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the different operations that can be performed on the SQL Server database by using the adapter.</span></span>  
  
 <span data-ttu-id="b993f-105">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="b993f-105">What is an adapter?</span></span> <span data-ttu-id="b993f-106">アダプターは、基幹業務 (LOB) システムとのメッセージを送受信することができるソフトウェア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b993f-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="b993f-107">アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を促進します。</span><span class="sxs-lookup"><span data-stu-id="b993f-107">The primary design goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="b993f-108">各ビジネス システムは、特定のドキュメント形式とプロトコルに従うことがあります、ため、アダプターは、一般的な規格と、ユーザーに統一インターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b993f-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="b993f-109">アダプター、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="b993f-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="b993f-110">**LOB アダプタ**します。</span><span class="sxs-lookup"><span data-stu-id="b993f-110">**LOB adapters**.</span></span> <span data-ttu-id="b993f-111">このようなアダプターへのアクセスの LOB システムへのサービス指向のプログラミング モデルを提供する、SAP や Siebel アダプターなど。</span><span class="sxs-lookup"><span data-stu-id="b993f-111">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="b993f-112">**データ アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="b993f-112">**Data adapters**.</span></span> <span data-ttu-id="b993f-113">このようなアダプターは、access データベースにサービス指向のプログラミング モデルを提供します。-Oracle database または SQL Server のアダプターなど。</span><span class="sxs-lookup"><span data-stu-id="b993f-113">Such adapters provide service-oriented programming model to access databases—for example, adapters for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="b993f-114">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b993f-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] <span data-ttu-id="b993f-115">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b993f-115">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b993f-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]が外部で利用可能でも、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]別個のアダプターとして。</span><span class="sxs-lookup"><span data-stu-id="b993f-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also available outside the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as a separate adapter.</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="b993f-117">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b993f-117">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="b993f-118">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b993f-118">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] <span data-ttu-id="b993f-119">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b993f-119">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] <span data-ttu-id="b993f-120">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b993f-120">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="b993f-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="b993f-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="b993f-122">いない既にわかっている場合、会社の SQL アダプタを使用する方法をお勧め、機能を開始してで説明されているアダプターの機能を[BizTalk Adapter for SQL Server に理解](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="b993f-122">If you do not already know how you want to use the SQL adapter at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b993f-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b993f-123">In This Section</span></span>  
  
-   [<span data-ttu-id="b993f-124">BizTalk Adapter for SQL Server を理解する</span><span class="sxs-lookup"><span data-stu-id="b993f-124">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="b993f-125">SQL アダプターのチュートリアル</span><span class="sxs-lookup"><span data-stu-id="b993f-125">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [<span data-ttu-id="b993f-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b993f-126">Frequently Asked Questions</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)