---
title: WCF を使用してポーリング Oracle E-business Suite のサービス モデル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96670a39-4fec-49bf-85d1-947b1a1bc750
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b48894e6e583c6cc622a44596d09b8191be726b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374876"
---
# <a name="poll-oracle-e-business-suite-using-the-wcf-service-model"></a><span data-ttu-id="4dee6-102">WCF サービス モデルを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="4dee6-102">Poll Oracle E-Business Suite using the WCF service model</span></span>
<span data-ttu-id="4dee6-103">構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリング ベースのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from the Oracle database.</span></span> <span data-ttu-id="4dee6-104">アダプターは、Oracle データベースをポーリングの 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="4dee6-105">**SELECT ステートメントを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-105">**Using SELECT statements**.</span></span> <span data-ttu-id="4dee6-106">Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4dee6-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="4dee6-107">アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="4dee6-108">**ストアド プロシージャを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-108">**Using stored procedures**.</span></span> <span data-ttu-id="4dee6-109">Oracle データベースをポーリングするストアド プロシージャを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="4dee6-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="4dee6-110">アダプターは、指定した間隔でストアド プロシージャを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="4dee6-111">2 つのアプローチの主な違いは、方法アダプターのクライアントは、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="4dee6-112">最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="4dee6-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="4dee6-113">アダプター クライアントのポーリング ステートメント、どちらの方法を指定して、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="4dee6-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="4dee6-114">バインド プロパティの詳細については、次を参照してください。 [Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
  <span data-ttu-id="4dee6-115">このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してポーリングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dee6-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4dee6-116">In This Section</span></span>  
  
-   [<span data-ttu-id="4dee6-117">SELECT ステートメントを使用して WCF サービス モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="4dee6-117">Poll Oracle E-Business Suite using SELECT statement with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="4dee6-118">ストアド プロシージャを使用して WCF サービス モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="4dee6-118">Poll Oracle E-Business Suite using stored procedures with the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures-with-the-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="4dee6-119">参照</span><span class="sxs-lookup"><span data-stu-id="4dee6-119">See Also</span></span>  
 [<span data-ttu-id="4dee6-120">WCF サービス モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="4dee6-120">Develop Oracle E-Business Suite applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)