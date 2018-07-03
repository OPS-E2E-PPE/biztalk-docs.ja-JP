---
title: BizTalk Adapter for mySAP Business Suite の概要 |Microsoft Docs
description: カスタム Rfc をインストール、アダプターについて、SAP、BizTalk アダプター パック (BAP) での mySAP アダプターを使用するチュートリアルの手順で RFC および IDOC のタスクを完了
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02112b6974a537c9f66cc301014ae16bb4bf326f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967473"
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="65395-103">BizTalk Adapter for mySAP Business Suite の概要します。</span><span class="sxs-lookup"><span data-stu-id="65395-103">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="65395-104">このセクションでは、ユーザーが Microsoft に新しいアダプター、前提条件、およびトピックの概要を示します[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="65395-104">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="65395-105">機能について説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とアダプターを使用して SAP システムで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="65395-105">It discusses the features of [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the different operations that can be performed on the SAP system using the adapter.</span></span>  

## <a name="what-is-an-adapter"></a><span data-ttu-id="65395-106">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="65395-106">What is an adapter?</span></span> 
<span data-ttu-id="65395-107">アダプターは、基幹業務 (LOB) システムとのメッセージを送受信することができるソフトウェア コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="65395-107">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="65395-108">アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を促進します。</span><span class="sxs-lookup"><span data-stu-id="65395-108">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="65395-109">各ビジネス システムは、特定のドキュメント形式とプロトコルに従うことがあります、ため、アダプターは、一般的な規格と、ユーザーに統一インターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65395-109">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="65395-110">アダプターは、2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="65395-110">The adapters can be divided into two broad categories:</span></span>  
  
- <span data-ttu-id="65395-111">**LOB アダプタ**します。</span><span class="sxs-lookup"><span data-stu-id="65395-111">**LOB adapters**.</span></span> <span data-ttu-id="65395-112">このようなアダプターへのアクセスの LOB システムへのサービス指向のプログラミング モデルを提供する、SAP や Siebel アダプターなど。</span><span class="sxs-lookup"><span data-stu-id="65395-112">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
- <span data-ttu-id="65395-113">**データ アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="65395-113">**Data adapters**.</span></span> <span data-ttu-id="65395-114">このようなアダプターは、access データベースにサービス指向のプログラミング モデルを提供 — たとえば、Oracle database または SQL Server のアダプター。</span><span class="sxs-lookup"><span data-stu-id="65395-114">Such adapters provide service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
  <span data-ttu-id="65395-115">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="65395-115">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
- [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="65395-116"> (、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="65395-116"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="65395-117"> (、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="65395-117"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
- [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="65395-118"> (、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="65395-118"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
- [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="65395-119"> (、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="65395-119"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
- [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="65395-120"> (、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="65395-120"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="65395-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="65395-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
  <span data-ttu-id="65395-122">かどうかは既にわからないを使用する方法、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で、社内をお勧めして機能の探索を開始してで説明されているアダプターの機能を[理解の BizTalk Adapter 用 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="65395-122">If you do not already know how you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] at your company, it is recommended that you start by exploring features and functionality of the adapter described in [Understand BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="65395-123">次のステップ</span><span class="sxs-lookup"><span data-stu-id="65395-123">Next steps</span></span>  
- [<span data-ttu-id="65395-124">Data Provider for SAP のカスタム RFC をインストールする</span><span class="sxs-lookup"><span data-stu-id="65395-124">Install Custom RFCs for the Data Provider for SAP</span></span>](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [<span data-ttu-id="65395-125">BizTalk Adapter for mySAP Business Suite について</span><span class="sxs-lookup"><span data-stu-id="65395-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [<span data-ttu-id="65395-126">SAP で RFC および IDOC のタスクを実行する</span><span class="sxs-lookup"><span data-stu-id="65395-126">Complete RFC and IDOC tasks on SAP</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [<span data-ttu-id="65395-127">SAP アダプター チュートリアル</span><span class="sxs-lookup"><span data-stu-id="65395-127">SAP Adapter Tutorials</span></span>](sap-adapter-tutorials.md)  