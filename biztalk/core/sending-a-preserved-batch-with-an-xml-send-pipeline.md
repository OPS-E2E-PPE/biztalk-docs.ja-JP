---
title: 送信パイプラインの XML による保存されたバッチの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ea7a208942895c11a633fa0a67ae583952db0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399047"
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a><span data-ttu-id="69b14-102">XML 送信パイプラインによる保存されたバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="69b14-102">Sending a Preserved Batch with an XML Send Pipeline</span></span>
<span data-ttu-id="69b14-103">通常、保存されたバッチは、EDI 送信パイプラインを使用して送信されます。</span><span class="sxs-lookup"><span data-stu-id="69b14-103">Normally, a preserved batch is sent using an EDI send pipeline.</span></span> <span data-ttu-id="69b14-104">ただし、保存されたバッチを送信するのに、XML 送信パイプラインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="69b14-104">However, you can also use an XML send pipeline to send a preserved batch.</span></span> <span data-ttu-id="69b14-105">生成され、EDI で、MessageBox にドロップされる保存されたバッチから受信パイプラインは、XML 形式では、XML 送信パイプラインは XML 形式のバッチを受け渡しします。</span><span class="sxs-lookup"><span data-stu-id="69b14-105">Since the preserved batch that is generated and dropped in the MessageBox by the EDI receive pipeline is in the XML format, the XML send pipeline would pass along the batch in XML format.</span></span>  
  
 <span data-ttu-id="69b14-106">XML 送信パイプラインを使用して、保存されたバッチを送信するには、該当するバッチ スキーマと、インターチェンジの各メッセージの種類のドキュメント スキーマを持つプロジェクトを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69b14-106">To send a preserved batch using the XML send pipeline, you have to deploy a project with the applicable batch schema and the document schemas for each message type in the interchange.</span></span> <span data-ttu-id="69b14-107">さらに、プロジェクト内に展開するバッチ スキーマの名前空間を変更する必要もします。</span><span class="sxs-lookup"><span data-stu-id="69b14-107">In addition, you also have to change the namespace for the batch schema that you deploy in the project.</span></span> <span data-ttu-id="69b14-108">これを行わない場合、保存されたバッチの XML ファイル内の名前空間は、バッチ スキーマの名前空間に対応していません。</span><span class="sxs-lookup"><span data-stu-id="69b14-108">If you do not do so, the namespace in the preserved batch XML file would not correspond to the namespace for the batch schema.</span></span> <span data-ttu-id="69b14-109">次の表に示すように、バッチ スキーマの名前空間を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69b14-109">You have to change the namespace for the batch schema as shown in the following table:</span></span>  
  
|<span data-ttu-id="69b14-110">このエンコードの種類。</span><span class="sxs-lookup"><span data-stu-id="69b14-110">For this encoding type:</span></span>|<span data-ttu-id="69b14-111">バッチ スキーマでこの名前空間を変更します。</span><span class="sxs-lookup"><span data-stu-id="69b14-111">Change this namespace in the batch schema:</span></span>|<span data-ttu-id="69b14-112">次の名前空間。</span><span class="sxs-lookup"><span data-stu-id="69b14-112">To the following namespace:</span></span>|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|<span data-ttu-id="69b14-113">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="69b14-113">EDIFACT</span></span>|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|<span data-ttu-id="69b14-114">X12</span><span class="sxs-lookup"><span data-stu-id="69b14-114">X12</span></span>|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 <span data-ttu-id="69b14-115">これは、EDI アセンブラーの問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="69b14-115">This is not an issue with the EDI Assembler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69b14-116">参照</span><span class="sxs-lookup"><span data-stu-id="69b14-116">See Also</span></span>  
 [<span data-ttu-id="69b14-117">EDI バッチの構成</span><span class="sxs-lookup"><span data-stu-id="69b14-117">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)