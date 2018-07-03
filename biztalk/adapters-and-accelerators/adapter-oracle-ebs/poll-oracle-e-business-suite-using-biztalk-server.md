---
title: BizTalk Server を使用してポーリング Oracle E-business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a22b99a5-1715-4351-b0e0-6b8dcfacd9eb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8180b3b671c87b5dcd0d41477e20b6d175f1cce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974219"
---
# <a name="poll-oracle-e-business-suite-using-biztalk-server"></a><span data-ttu-id="6ae10-102">BizTalk Server を使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="6ae10-102">Poll Oracle E-Business Suite using BizTalk Server</span></span>
<span data-ttu-id="6ae10-103">構成することができます、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle データベースからのポーリング ベースのメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-103">You can configure the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to receive polling-based messages from Oracle database.</span></span> <span data-ttu-id="6ae10-104">アダプターは、Oracle データベースをポーリングの 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-104">The adapter provides two ways of polling the Oracle database:</span></span>  
  
- <span data-ttu-id="6ae10-105">**SELECT ステートメントを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-105">**Using SELECT statements**.</span></span> <span data-ttu-id="6ae10-106">Oracle データベースをポーリングする単純な SELECT ステートメントを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6ae10-106">You can specify a simple SELECT statement to poll the Oracle database.</span></span> <span data-ttu-id="6ae10-107">アダプターは、指定した間隔で SELECT ステートメントを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-107">The adapter executes the SELECT statement at specified intervals and returns the result to the adapter clients.</span></span>  
  
- <span data-ttu-id="6ae10-108">**ストアド プロシージャを使用して**します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-108">**Using stored procedures**.</span></span> <span data-ttu-id="6ae10-109">Oracle データベースをポーリングするストアド プロシージャを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="6ae10-109">You can specify a stored procedure to poll the Oracle database.</span></span> <span data-ttu-id="6ae10-110">アダプターは、指定した間隔でストアド プロシージャを実行し、アダプターのクライアントに結果を返します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-110">The adapter executes the stored procedure at specified intervals and returns the result to the adapter clients.</span></span>  
  
  <span data-ttu-id="6ae10-111">2 つのアプローチの主な違いは、方法アダプターのクライアントは、アダプターを使用して Oracle データベースをポーリングするポーリング ステートメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-111">The key difference in the two approaches is the way adapter clients specify a polling statement that the adapter uses to poll the Oracle database.</span></span> <span data-ttu-id="6ae10-112">最初の方法のポーリング ステートメントには、単純な SELECT ステートメントが、ストアド プロシージャのアプローチのポーリング ステートメント、ストアド プロシージャを実行する要求メッセージです。</span><span class="sxs-lookup"><span data-stu-id="6ae10-112">While the polling statement for the first approach is a simple SELECT statement, the polling statement for the stored procedure approach is a request message that executes the stored procedure.</span></span> <span data-ttu-id="6ae10-113">アダプター クライアントのポーリング ステートメント、どちらの方法を指定して、 **PollingInput**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="6ae10-113">Adapter clients specify the polling statement, for either approach, for the **PollingInput** binding property.</span></span> <span data-ttu-id="6ae10-114">バインド プロパティの詳細については、次を参照してください。[については、BizTalk Adapter for Oracle E-business Suite バインド プロパティを読み取る](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-114">For more information about the binding properties, see [Read about the BizTalk Adapter for Oracle E-Business Suite Binding Properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
  <span data-ttu-id="6ae10-115">このセクションのトピックでは、SELECT ステートメントおよびストアド プロシージャを使用してポーリングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-115">The topics in this section provide instructions on how to poll using a SELECT statement and a stored procedure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ae10-116">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6ae10-116">In This Section</span></span>  
  
-   [<span data-ttu-id="6ae10-117">SELECT ステートメントを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="6ae10-117">Poll Oracle E-Business Suite Using SELECT Statement</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md)  
  
-   [<span data-ttu-id="6ae10-118">ストアド プロシージャを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="6ae10-118">Poll Oracle E-Business Suite Using Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-stored-procedures.md)  
  
## <a name="see-also"></a><span data-ttu-id="6ae10-119">参照</span><span class="sxs-lookup"><span data-stu-id="6ae10-119">See Also</span></span>  
[<span data-ttu-id="6ae10-120">Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="6ae10-120">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md)