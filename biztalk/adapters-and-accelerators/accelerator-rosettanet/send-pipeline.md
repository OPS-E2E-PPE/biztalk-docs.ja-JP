---
title: "送信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58ca6a63-525a-4b16-932d-6d26e68f6fab
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b36340d241ac52fe4fb7f10025807f386c51a8ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="send-pipeline"></a><span data-ttu-id="4a846-102">送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="4a846-102">Send Pipeline</span></span>
<span data-ttu-id="4a846-103">このサンプルは、独自のアプリケーション用にカスタマイズできる [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="4a846-103">This sample provides a working [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] send pipeline that you can customize for your application.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="4a846-104">使用例</span><span class="sxs-lookup"><span data-stu-id="4a846-104">Demonstrates</span></span>  
 <span data-ttu-id="4a846-105">このサンプルは、BTARN 送信パイプライン (PipelineSend.btp) を使用して、XML 送信メッセージを同等の RNIF メッセージに処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4a846-105">This sample demonstrates how to process an outgoing XML message into the equivalent RNIF message using the BTARN send pipeline (PipelineSend.btp).</span></span> <span data-ttu-id="4a846-106">PipelineSend.btp にあります*\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\rnpipelines です。</span><span class="sxs-lookup"><span data-stu-id="4a846-106">PipelineSend.btp is located in *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="4a846-107">このサンプルには次のステージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a846-107">It includes the following stages:</span></span>  
  
-   <span data-ttu-id="4a846-108">XML アセンブラー</span><span class="sxs-lookup"><span data-stu-id="4a846-108">XML Assembler</span></span>  
  
-   <span data-ttu-id="4a846-109">MIME エンコーダー</span><span class="sxs-lookup"><span data-stu-id="4a846-109">MIME Encoder</span></span>  
  
-   <span data-ttu-id="4a846-110">送信メッセージ否認不可</span><span class="sxs-lookup"><span data-stu-id="4a846-110">Send message Non-repudiate</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a846-111">Visual Studio のパイプライン デザイナーで、上記の BTARN 送信パイプラインのコンポーネントのいずれかを選択しても、そのコンポーネントのプロパティは [プロパティ] ペインには表示されません。</span><span class="sxs-lookup"><span data-stu-id="4a846-111">If you select one of the above components of the BTARN send pipeline in the Pipeline Designer in Visual Studio, the properties for that component will not be displayed in the Properties pane.</span></span> <span data-ttu-id="4a846-112">コンポーネントのプロパティを表示する必要があります、コンポーネントを追加する、ツールボックスを使用して、**ツールボックス アイテムの選択**ツール メニューにコマンド以外の場合は、送信パイプラインから既存のコンポーネントを削除しからのコンポーネントを追加しますパイプライン デザイナーで適切なステージにツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="4a846-112">To display the properties of the component, you must add the component to the Toolbox by using the **Choose Toolbox Items** command in the Tools menu; delete the existing component from the send pipeline; and then add the component from the Toolbox into the appropriate stage in the Pipeline Designer.</span></span> <span data-ttu-id="4a846-113">コンポーネントを選択すると、そのコンポーネントのプロパティが [プロパティ] ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a846-113">If you then select the component, its properties will be displayed in the Properties pane.</span></span>  
  
 <span data-ttu-id="4a846-114">このパイプラインおよびパイプライン内のメッセージ フローのコンポーネントに関する詳細については、次を参照してください。 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)です。</span><span class="sxs-lookup"><span data-stu-id="4a846-114">For more information about the components of this pipeline, and the message flow within this pipeline, see [BTARN Send Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a846-115">参照</span><span class="sxs-lookup"><span data-stu-id="4a846-115">See Also</span></span>  
 <span data-ttu-id="4a846-116">[パイプラインのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span><span class="sxs-lookup"><span data-stu-id="4a846-116">[Pipeline Samples](../../adapters-and-accelerators/accelerator-rosettanet/pipeline-samples.md) </span></span>  
 [<span data-ttu-id="4a846-117">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="4a846-117">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)