---
title: WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発 |Microsoft ドキュメント
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
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214802"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a><span data-ttu-id="e0938-102">WCF チャネル モデルを使用して Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e0938-102">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>
<span data-ttu-id="e0938-103">使用することができます、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]チャネル モデルを使用する、 [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle EBS バインドで作成されたチャネル インスタンス経由で直接 XML メッセージを送信することによってです。</span><span class="sxs-lookup"><span data-stu-id="e0938-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] by sending XML messages directly over a channel instance created with the Oracle EBS Binding.</span></span>  
  
 <span data-ttu-id="e0938-104">WCF チャネル モデルを使用して、厳密に型指定されたクラスとモデルが公開する WCF サービス、チャネル モデルに Oracle E-business Suite で実行する操作をより詳細に制御が用意されているメソッドの使用上の利点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e0938-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle E-Business Suite.</span></span> <span data-ttu-id="e0938-105">このコントロールは、ファクトのことで、WCF チャネル モデルを直接制御するチャネル経由で送信するメッセージの内容から取得されます。</span><span class="sxs-lookup"><span data-stu-id="e0938-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="e0938-106">特定のシナリオでは、この余分なレベルの制御と役に立つことがあります。</span><span class="sxs-lookup"><span data-stu-id="e0938-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="e0938-107">たとえば、WCF チャネル モデルを使用して、テーブルの更新操作を実行するときに、ターゲット行の列をメッセージを渡すテンプレートの更新からの列を省略することでに更新できます選択的にします。</span><span class="sxs-lookup"><span data-stu-id="e0938-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="e0938-108">必要な列のみが"nillable = false"、WSDL でします。</span><span class="sxs-lookup"><span data-stu-id="e0938-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="e0938-109">によって公開されている、update メソッドを[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]クライアントは、テーブルのスキーマ内のすべての列を含むテンプレートに対してレコードの厳密に型指定されたパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0938-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="e0938-110">このセクションのトピックでの操作を実行する方法を説明する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] WCF チャネル モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0938-110">The topics in this section explain how to perform operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0938-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e0938-111">In This Section</span></span>  
  
-   [<span data-ttu-id="e0938-112">Oracle E-business Suite アダプターで WCF チャネル モデルの概要</span><span class="sxs-lookup"><span data-stu-id="e0938-112">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="e0938-113">Oracle E-business Suite を使用して、チャネルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0938-113">Create a channel using Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [<span data-ttu-id="e0938-114">WCF チャネル モデルを使用して Oracle E-business suite のインターフェイス テーブルに対して挿入操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0938-114">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="e0938-115">WCF チャネル モデルを含む SELECT ステートメントを使用してポーリング Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="e0938-115">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a><span data-ttu-id="e0938-116">参照</span><span class="sxs-lookup"><span data-stu-id="e0938-116">See Also</span></span>  
[<span data-ttu-id="e0938-117">Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="e0938-117">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)