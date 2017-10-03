---
title: "BizTalk Adapter 用 mySAP Business Suite の概要 |Microsoft ドキュメント"
description: "カスタム Rfc のインストール、アダプターについて、SAP、mySAP アダプターの BizTalk アダプター パック (BAP) を使用するチュートリアルのステップでタスクを RFC および IDOC 完了"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2013253-f911-4e35-a33a-b4a9bcb136aa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e5607a255f50bf5295d4ea22c9a680d86f38e5b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-started-with-the-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="9d002-103">BizTalk Adapter 用 mySAP Business Suite の概要します。</span><span class="sxs-lookup"><span data-stu-id="9d002-103">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="9d002-104">このセクションでは Microsoft に新しいユーザーのアダプター、前提条件、およびトピックの概要を説明する[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="9d002-104">This section provides an overview of the adapter, prerequisites, and topics for users who are new to Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="9d002-105">機能についても説明[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]とアダプターを使用して SAP システムで実行できるさまざまな操作です。</span><span class="sxs-lookup"><span data-stu-id="9d002-105">It discusses the features of [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the different operations that can be performed on the SAP system using the adapter.</span></span>  

## <a name="what-is-an-adapter"></a><span data-ttu-id="9d002-106">アダプターとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9d002-106">What is an adapter?</span></span> 
<span data-ttu-id="9d002-107">アダプターは、ソフトウェア コンポーネントと基幹業務 (LOB) システムからメッセージを送受信することができます。</span><span class="sxs-lookup"><span data-stu-id="9d002-107">An adapter is a software component that enables you to send and receive messages to and from a line-of-business (LOB) system.</span></span> <span data-ttu-id="9d002-108">アダプターの主な設計目標は、取引先間でのビジネス ドキュメントの交換を容易にです。</span><span class="sxs-lookup"><span data-stu-id="9d002-108">The primary design goal of adapters is to facilitate the exchange of business documents between trading partners.</span></span> <span data-ttu-id="9d002-109">各ビジネス システムは、特定のドキュメント形式およびプロトコルに従うことがあります、ために、アダプターは、共通に認識される標準と、ユーザーに一貫したインターフェイスを提供するプロトコルに準拠した配信メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d002-109">Because each business system may adhere to specific document formats and protocols, the adapter must use a delivery mechanism that conforms to commonly recognized standards and protocols to provide a uniform interface to the users.</span></span>  
  
 <span data-ttu-id="9d002-110">アダプターは、2 つのカテゴリに分類できます。</span><span class="sxs-lookup"><span data-stu-id="9d002-110">The adapters can be divided into two broad categories:</span></span>  
  
-   <span data-ttu-id="9d002-111">**LOB アダプタ**です。</span><span class="sxs-lookup"><span data-stu-id="9d002-111">**LOB adapters**.</span></span> <span data-ttu-id="9d002-112">このようなアダプターが LOB システムへのアクセスをサービス指向のプログラミング モデルを提供、SAP の Siebel アダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="9d002-112">Such adapters provide service-oriented programming model to access LOB systems—for example, adapters for SAP or Siebel.</span></span>  
  
-   <span data-ttu-id="9d002-113">**データ アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="9d002-113">**Data adapters**.</span></span> <span data-ttu-id="9d002-114">このようなアダプターがデータベースにアクセスできるサービス指向のプログラミング モデルを提供、Oracle データベースまたは SQL Server 用のアダプターなどです。</span><span class="sxs-lookup"><span data-stu-id="9d002-114">Such adapters provide service-oriented programming model to access databases—for example, an adapter for the Oracle database or SQL Server.</span></span>  
  
 <span data-ttu-id="9d002-115">5 つのアダプタでは、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9d002-115">There are five adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]<span data-ttu-id="9d002-116">(、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9d002-116"> (the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]<span data-ttu-id="9d002-117">(、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9d002-117"> (the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)])</span></span>  
  
-   [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="9d002-118">(、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9d002-118"> (the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]<span data-ttu-id="9d002-119">(、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]) など、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9d002-119"> (the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]), including [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])</span></span>  
  
-   [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]<span data-ttu-id="9d002-120">(、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]) など、 [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span><span class="sxs-lookup"><span data-stu-id="9d002-120"> (the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]), including [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9d002-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] 64 ビット プラットフォームでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="9d002-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is not available for 64-bit platforms.</span></span>  
  
 <span data-ttu-id="9d002-122">かどうかは既に分かっていなければを使用する方法、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で、社内をお勧めする機能を表示することによって起動してで説明されているアダプターの機能[BizTalk Adapter 用 mySAP Business Suite 理解](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="9d002-122">If you do not already know how you want to use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] at your company, it is recommended that you start by exploring features and functionality of the adapter described in [Understand BizTalk Adapter for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9d002-123">次の手順</span><span class="sxs-lookup"><span data-stu-id="9d002-123">Next steps</span></span>  
- [<span data-ttu-id="9d002-124">SAP 用データ プロバイダーのカスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9d002-124">Install Custom RFCs for the Data Provider for SAP</span></span>](install-custom-rfcs-for-the-data-provider-for-sap.md)
  
-   [<span data-ttu-id="9d002-125">MySAP Business Suite の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="9d002-125">Understand BizTalk Adapter for mySAP Business Suite</span></span>](understand-biztalk-adapter-for-mysap-business-suite.md)  

- [<span data-ttu-id="9d002-126">SAP での RFC および IDOC のタスクを完了</span><span class="sxs-lookup"><span data-stu-id="9d002-126">Complete RFC and IDOC tasks on SAP</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)
  
-   [<span data-ttu-id="9d002-127">SAP アダプタ チュートリアル</span><span class="sxs-lookup"><span data-stu-id="9d002-127">SAP Adapter Tutorials</span></span>](sap-adapter-tutorials.md)  