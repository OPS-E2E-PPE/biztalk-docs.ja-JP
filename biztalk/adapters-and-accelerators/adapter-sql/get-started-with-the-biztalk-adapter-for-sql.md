---
title: "SQL 用 BizTalk アダプターの概要 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c3b6e36-ddfb-4ede-adf5-b9762231224b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61a2ecd7ae8020865dff7b67fbc57388d1f15af6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-sql"></a><span data-ttu-id="6e724-102">SQL 用 BizTalk アダプターを概要します。</span><span class="sxs-lookup"><span data-stu-id="6e724-102">Get started with the BizTalk adapter for SQL</span></span>

  
 <span data-ttu-id="6e724-103">このセクションでは Microsoft に新しいユーザーのアダプター、前提条件、およびトピックの概要を説明する[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6e724-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="6e724-104">機能についても説明[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]とアダプターを使用して SQL Server データベースで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="6e724-104">It discusses the features of [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the different operations that can be performed on the SQL Server database by using the adapter.</span></span>  
  
 <span data-ttu-id="6e724-105">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="6e724-105">What is an adapter?</span></span> <span data-ttu-id="6e724-106">アダプターは、ソフトウェア コンポーネントと基幹業務 (LOB) システムからメッセージを送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="6e724-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="6e724-107">アダプターの主な設計目標は、取引先間のビジネス ドキュメントの交換を容易にすることです。</span><span class="sxs-lookup"><span data-stu-id="6e724-107">The primary design goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="6e724-108">各ビジネス システムは、特定のドキュメント形式およびプロトコルに従うことがあります、ために、アダプターは、共通に認識される標準と、ユーザーに一貫したインターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e724-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="6e724-109">アダプター、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="6e724-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="6e724-110">**LOB アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="6e724-110">**LOB adapters**.</span></span> <span data-ttu-id="6e724-111">このようなアダプターが LOB システムへのアクセスをサービス指向のプログラミング モデルを提供、SAP の Siebel アダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="6e724-111">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="6e724-112">**データ アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="6e724-112">**Data adapters**.</span></span> <span data-ttu-id="6e724-113">このようなアダプターがデータベースにアクセスできるサービス指向のプログラミング モデルを提供、Oracle データベースまたは SQL Server のアダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="6e724-113">Such adapters provide service-oriented programming model to access databases—for example, adapters for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="6e724-114">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="6e724-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="6e724-115"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e724-115"> ([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e724-116">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は外部で利用可能でも、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]別個のアダプターとして。</span><span class="sxs-lookup"><span data-stu-id="6e724-116">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is also available outside the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as a separate adapter.</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="6e724-117"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e724-117"> ([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]).</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="6e724-118"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e724-118"> ([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]).</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="6e724-119"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e724-119"> ([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]).</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="6e724-120"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="6e724-120"> ([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e724-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e724-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="6e724-122">機能を表示することによって起動してで説明されているアダプターの機能をお勧めする既に知らない場合、会社への SQL アダプターを使用する方法、 [for SQL Server の BizTalk アダプターの理解](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="6e724-122">If you do not already know how you want to use the SQL adapter at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e724-123">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6e724-123">In This Section</span></span>  
  
-   [<span data-ttu-id="6e724-124">SQL Server の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="6e724-124">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="6e724-125">SQL アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6e724-125">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)  
  
-   [<span data-ttu-id="6e724-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6e724-126">Frequently Asked Questions</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-faqs.md)