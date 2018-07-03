---
title: Oracle データベース アダプターの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, about
- data adapter
- LOB adapter
ms.assetid: ed5b3510-11c4-4b10-bf85-c4066f3f80df
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daead7b52c17fe5a045d6681a7aa957aaa23133c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966859"
---
# <a name="get-started-with-the-oracle-database-adapter"></a><span data-ttu-id="2bbdb-102">Oracle データベース アダプターを概要します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-102">Get started with the Oracle Database adapter</span></span>
<span data-ttu-id="2bbdb-103">このセクションでは、ユーザーが Microsoft に新しいアダプター、前提条件、およびトピックの概要を示します[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-103">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="2bbdb-104">機能について説明します[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]とアダプターを使用して Oracle データベースで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-104">It discusses the features of [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the different operations that can be performed on the Oracle database using the adapter.</span></span>  
  
 <span data-ttu-id="2bbdb-105">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-105">What is an adapter?</span></span> <span data-ttu-id="2bbdb-106">アダプターは、基幹業務 (LOB) システムとのメッセージを送受信することができるソフトウェア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="2bbdb-107">アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を促進します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-107">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="2bbdb-108">各ビジネス システムは、特定のドキュメント形式とプロトコルに従うことができます、ため、アダプターは、一般的な規格とプロトコルに準拠した配信メカニズムを使用します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-108">Because each business system can adhere to specific document formats and protocols, the adapter uses a delivery mechanism that conforms to commonly recognized standards and protocols.</span></span>  
  
 <span data-ttu-id="2bbdb-109">アダプターは、2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-109">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="2bbdb-110">**LOB アダプタ**します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-110">**LOB adapters**.</span></span> <span data-ttu-id="2bbdb-111">このようなアダプターへのアクセスの LOB システムへのサービス指向のプログラミング モデルを提供する、SAP や Siebel アダプターなど。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-111">Such adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="2bbdb-112">**データ アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-112">**Data adapters**.</span></span> <span data-ttu-id="2bbdb-113">このようなアダプターは、access データベースにサービス指向のプログラミング モデルを提供 — たとえば、Oracle database または SQL Server のアダプター。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-113">Such adapters provide a service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="2bbdb-114">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2bbdb-114">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="2bbdb-115"> (、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2bbdb-115"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="2bbdb-116"> (、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2bbdb-116"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="2bbdb-117"> (、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2bbdb-117"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="2bbdb-118"> (、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2bbdb-118"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="2bbdb-119"> (、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="2bbdb-119"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2bbdb-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2bbdb-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="2bbdb-121">かどうかは既にわからないを使用する方法、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で、社内をお勧め、機能を開始してで説明されているアダプターの機能を[のOracleデータベースのBizTalkアダプターの理解](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="2bbdb-121">If you do not already know how you want to use the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] at your company, it is recommended that you start by exploring the features and functionality of the adapter described in [Understanding the BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md).</span></span>  
  
