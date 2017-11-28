---
title: "XML に保存されたバッチを送信する送信パイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6765576a-134f-4856-911c-2f603b6479bd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 14bd61538398bb11967cbbe750a4fadc016a5168
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sending-a-preserved-batch-with-an-xml-send-pipeline"></a><span data-ttu-id="b54a2-102">XML 送信パイプラインによる保存されたバッチの送信</span><span class="sxs-lookup"><span data-stu-id="b54a2-102">Sending a Preserved Batch with an XML Send Pipeline</span></span>
<span data-ttu-id="b54a2-103">通常、保存されたバッチは、EDI 送信パイプラインを使用して送信します。</span><span class="sxs-lookup"><span data-stu-id="b54a2-103">Normally, a preserved batch is sent using an EDI send pipeline.</span></span> <span data-ttu-id="b54a2-104">ただし、XML 送信パイプラインを使用して、保存されたバッチを送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="b54a2-104">However, you can also use an XML send pipeline to send a preserved batch.</span></span> <span data-ttu-id="b54a2-105">EDI 受信パイプラインによって生成され、メッセージ ボックスにドロップされる場合の保存されたバッチは XML 形式であるため、XML 送信パイプラインでは、このバッチを XML 形式で渡します。</span><span class="sxs-lookup"><span data-stu-id="b54a2-105">Since the preserved batch that is generated and dropped in the MessageBox by the EDI receive pipeline is in the XML format, the XML send pipeline would pass along the batch in XML format.</span></span>  
  
 <span data-ttu-id="b54a2-106">XML 送信パイプラインを使用して、保存されたバッチを送信するには、該当するバッチ スキーマと、インターチェンジの各メッセージの種類のドキュメント スキーマを持つプロジェクトを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54a2-106">To send a preserved batch using the XML send pipeline, you have to deploy a project with the applicable batch schema and the document schemas for each message type in the interchange.</span></span> <span data-ttu-id="b54a2-107">また、プロジェクトで展開するバッチ スキーマの名前空間を変更することも必要です。</span><span class="sxs-lookup"><span data-stu-id="b54a2-107">In addition, you also have to change the namespace for the batch schema that you deploy in the project.</span></span> <span data-ttu-id="b54a2-108">これを行わないと、保存されたバッチの XML ファイルがバッチ スキーマの名前空間と対応しなくなります。</span><span class="sxs-lookup"><span data-stu-id="b54a2-108">If you do not do so, the namespace in the preserved batch XML file would not correspond to the namespace for the batch schema.</span></span> <span data-ttu-id="b54a2-109">バッチ スキーマの名前空間は、次の表に示すように変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b54a2-109">You have to change the namespace for the batch schema as shown in the following table:</span></span>  
  
|<span data-ttu-id="b54a2-110">このエンコードの種類。</span><span class="sxs-lookup"><span data-stu-id="b54a2-110">For this encoding type:</span></span>|<span data-ttu-id="b54a2-111">バッチ スキーマの変更前の名前空間</span><span class="sxs-lookup"><span data-stu-id="b54a2-111">Change this namespace in the batch schema:</span></span>|<span data-ttu-id="b54a2-112">変更後の名前空間</span><span class="sxs-lookup"><span data-stu-id="b54a2-112">To the following namespace:</span></span>|  
|-----------------------------|------------------------------------------------|---------------------------------|  
|<span data-ttu-id="b54a2-113">EDIFACT</span><span class="sxs-lookup"><span data-stu-id="b54a2-113">EDIFACT</span></span>|`http://schemas.microsoft.com/Edi/Edifact`|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006/InterchangeXML`|  
|<span data-ttu-id="b54a2-114">X12</span><span class="sxs-lookup"><span data-stu-id="b54a2-114">X12</span></span>|`http://schemas.microsoft.com/Edi/X12_BatchSchema`|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006/InterchangeXML`|  
  
 <span data-ttu-id="b54a2-115">これは、EDI アセンブラーの問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="b54a2-115">This is not an issue with the EDI Assembler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b54a2-116">参照</span><span class="sxs-lookup"><span data-stu-id="b54a2-116">See Also</span></span>  
 [<span data-ttu-id="b54a2-117">EDI バッチの構成</span><span class="sxs-lookup"><span data-stu-id="b54a2-117">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)