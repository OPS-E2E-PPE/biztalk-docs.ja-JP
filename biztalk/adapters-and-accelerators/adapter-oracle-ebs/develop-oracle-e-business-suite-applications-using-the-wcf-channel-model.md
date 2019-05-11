---
title: WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50e2f8ad108f056dda89328ae2c680cce708956
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375558"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a><span data-ttu-id="e2df7-102">WCF チャネル モデルを使用して Oracle E-business Suite のアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e2df7-102">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>
<span data-ttu-id="e2df7-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle EBS のバインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することです。</span><span class="sxs-lookup"><span data-stu-id="e2df7-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] by sending XML messages directly over a channel instance created with the Oracle EBS Binding.</span></span>  
  
 <span data-ttu-id="e2df7-104">WCF チャネル モデルを使用して、厳密に型指定されたクラスとチャネル モデルが Oracle E-business suite を実行する操作のきめの細かい制御を提供する WCF サービス モデルの公開は、メソッドの使用上の利点の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="e2df7-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle E-Business Suite.</span></span> <span data-ttu-id="e2df7-105">このコントロールは、ファクトのことで WCF チャネル モデルを直接制御チャネル経由で送信するメッセージの内容から取得されます。</span><span class="sxs-lookup"><span data-stu-id="e2df7-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="e2df7-106">特定のシナリオでこの追加レベルの制御はパフォーマンスを向上することはできます。</span><span class="sxs-lookup"><span data-stu-id="e2df7-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="e2df7-107">たとえば、WCF チャネル モデルを使用して、テーブルに対する Update 操作を実行するときに選択的に更新できますターゲット行内の列、メッセージを渡すテンプレートの更新からの列を省略することで。</span><span class="sxs-lookup"><span data-stu-id="e2df7-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="e2df7-108">必要な列のみが"nillable = false"、WSDL でします。</span><span class="sxs-lookup"><span data-stu-id="e2df7-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="e2df7-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントで、テーブルのスキーマ内のすべての列を含むテンプレートのレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e2df7-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="e2df7-110">このセクションのトピックでは、操作を実行する方法を説明します、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF チャネル モデルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e2df7-110">The topics in this section explain how to perform operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2df7-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e2df7-111">In This Section</span></span>  
  
-   [<span data-ttu-id="e2df7-112">Oracle E-business Suite アダプターを使用した WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="e2df7-112">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="e2df7-113">Oracle E-business Suite を使用してチャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2df7-113">Create a channel using Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [<span data-ttu-id="e2df7-114">WCF チャネル モデルを使用して Oracle E-business Suite でのインターフェイス テーブルで挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e2df7-114">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e2df7-115">SELECT ステートメントを使用して、WCF チャネル モデルとポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="e2df7-115">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a><span data-ttu-id="e2df7-116">参照</span><span class="sxs-lookup"><span data-stu-id="e2df7-116">See Also</span></span>  
[<span data-ttu-id="e2df7-117">Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e2df7-117">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)