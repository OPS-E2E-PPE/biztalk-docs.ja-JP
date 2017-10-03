---
title: "Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d201987490d9395b07d043c67fa50a31400fe7cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="65e72-102">Oracle E-business Suite アダプターを使用して BizTalk アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="65e72-102">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="65e72-103">BizTalk アプリケーションの開発で BizTalk プロジェクトを作成する[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]を使用して、  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** または **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  XML スキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="65e72-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and using the **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** or **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** to generate XML schema.</span></span> <span data-ttu-id="65e72-104">スキーマが生成されると、コンテンツ ベースのルーティング (CBR) を使用するか、生成されたスキーマに準拠するメッセージを送受信する BizTalk オーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="65e72-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to your generated schema.</span></span>  
  
 <span data-ttu-id="65e72-105">CBR は、ここで、Oracle E-business Suite に送信されるメッセージには、処理を要する処理は不要のシナリオで使用できます。</span><span class="sxs-lookup"><span data-stu-id="65e72-105">CBR can be used in scenarios where the messages being sent to Oracle E-Business Suite do not require any intensive processing.</span></span> <span data-ttu-id="65e72-106">たとえば、特定の型だけの受信ポート受信メッセージ、できることがわかっている場合、送信ポートにフィルター式に一致するメッセージをルーティングする送信ポートにフィルターを追加します。</span><span class="sxs-lookup"><span data-stu-id="65e72-106">For example, if you know that the receive port receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  

## <a name="use-orchestration"></a><span data-ttu-id="65e72-107">オーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="65e72-107">Use orchestration</span></span>  
 <span data-ttu-id="65e72-108">、BizTalk オーケストレーションの送信を作成およびとの間でメッセージを送受信する受信ポート、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、さらに、メッセージを送信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="65e72-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> 
 
 <span data-ttu-id="65e72-109">このセクションでは、BizTalk オーケストレーションを使用して、タスクおよび Oracle E-business Suite を使用して操作を実行する方法の情報を提供、[!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="65e72-109">This section provides information about using BizTalk orchestrations to perform tasks and operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="65e72-110">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]順番に使用して、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF バインドと対話することができます。</span><span class="sxs-lookup"><span data-stu-id="65e72-110">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65e72-111">使用する、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、常に設定する必要があります、 **EnableBizTalkCompatibilityMode**にプロパティのバインド**True**です。</span><span class="sxs-lookup"><span data-stu-id="65e72-111">To use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="65e72-112">手順については、次を参照してください。 [for Oracle E-business Suite のバインドのプロパティを構成する](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)です。</span><span class="sxs-lookup"><span data-stu-id="65e72-112">For the steps, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="65e72-113">参照</span><span class="sxs-lookup"><span data-stu-id="65e72-113">See Also</span></span>  
[<span data-ttu-id="65e72-114">Oracle E-business Suite アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="65e72-114">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)