---
title: Oracle E-business Suite 用 BizTalk アダプターの概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 852d5855-c58a-4fa3-8efd-6afea9e527df
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c32bfb27935bc93163bd777d0c604a0c08f303a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530707"
---
# <a name="get-started-with-the-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="9f3b7-102">Oracle E-business Suite 用 BizTalk アダプターの概要します。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-102">Get started with the BizTalk Adapter for Oracle E-Business Suite</span></span>
<span data-ttu-id="9f3b7-103">アダプター、前提条件、および初心者 Microsoft BizTalk Adapter Pack にはユーザー向けのトピックの概要です。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-103">Overview of the adapter, prerequisites, and topics for users who are new to Microsoft BizTalk Adapter Pack.</span></span> <span data-ttu-id="9f3b7-104">機能に関する情報が提供[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]と、アダプターを使用して Oracle データベースで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-104">Information is provided about the features of [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] and the different operations that can be performed on the Oracle database by using the adapter.</span></span>  
  
## <a name="what-is-an-adapter"></a><span data-ttu-id="9f3b7-105">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-105">What is an adapter?</span></span>  
  
 <span data-ttu-id="9f3b7-106">アダプターは、基幹業務 (LOB) システムとのメッセージを送受信することができるソフトウェア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-106">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="9f3b7-107">アダプターの主な目的は、取引先間でのビジネス ドキュメントの交換を促進します。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-107">The primary goal of an adapter is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="9f3b7-108">各ビジネス システムは、特定のドキュメント形式とプロトコルに従うことがあります、ため、アダプターは、一般的な規格と、ユーザーに統一インターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-108">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="9f3b7-109">アダプター、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-109">The adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="9f3b7-110">**LOB アダプタ**:LOB アダプタは、LOB システムへのアクセスをサービス指向のプログラミング モデルを提供、SAP や Siebel アプリケーション用のアダプターなど。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-110">**LOB adapters**: LOB adapters provide a service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel applications.</span></span>  
  
- <span data-ttu-id="9f3b7-111">**データ アダプター**:データ アダプターは、access データベースにサービス指向のプログラミング モデルを提供します。-Oracle database または SQL Server のアダプターなど。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-111">**Data adapters**: Data adapters provide a service-oriented programming model to access databases — for example, adapters for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="9f3b7-112">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9f3b7-112">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] <span data-ttu-id="9f3b7-113">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9f3b7-113">([!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] <span data-ttu-id="9f3b7-114">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9f3b7-114">([!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="9f3b7-115">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9f3b7-115">([!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] <span data-ttu-id="9f3b7-116">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9f3b7-116">([!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] <span data-ttu-id="9f3b7-117">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9f3b7-117">([!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9f3b7-118">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-118">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="9f3b7-119">慣れていない場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の機能を開始してで説明されているアダプターの機能をお勧めし、 [BizTalk Adapter for Oracle E-business Suite に理解](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-119">If you are new to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], then we recommend you start by exploring the features and functionality of the adapter described in [Understand BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f3b7-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9f3b7-120">In this section</span></span>  
  
-   [<span data-ttu-id="9f3b7-121">BizTalk Adapter for Oracle E-Business Suite について</span><span class="sxs-lookup"><span data-stu-id="9f3b7-121">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="9f3b7-122">チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="9f3b7-122">Tutorial: Presenting data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Presenting%20Data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)
  
- [<span data-ttu-id="9f3b7-123">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9f3b7-123">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)