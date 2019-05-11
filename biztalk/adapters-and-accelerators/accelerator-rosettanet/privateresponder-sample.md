---
title: PrivateResponder サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3137fadd-9582-4cc6-acfb-c44aca636950
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a02d4b2d902f2dad24a20c150e474e671f582a66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282520"
---
# <a name="privateresponder-sample"></a><span data-ttu-id="4491e-102">PrivateResponder サンプル</span><span class="sxs-lookup"><span data-stu-id="4491e-102">PrivateResponder Sample</span></span>
<span data-ttu-id="4491e-103">PrivateResponder.odx サンプルには、Microsoft® によってインストールされる応答側プライベート プロセスのコードが含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="4491e-103">The PrivateResponder.odx sample contains the code for the responder private process installed by Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)].</span></span> <span data-ttu-id="4491e-104">この汎用プライベート プロセスは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="4491e-104">This generic private process sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="4491e-105">既定で、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってサンプルでは、 \<*ドライブ*>: \Program Files\\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \sdk\PrivateResponder します。</span><span class="sxs-lookup"><span data-stu-id="4491e-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*>:\Program Files\\Microsoft  BizTalk \<version> Accelerator for RosettaNet\SDK\PrivateResponder.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="4491e-106">サンプルの内容</span><span class="sxs-lookup"><span data-stu-id="4491e-106">Sample Contents</span></span>  
 <span data-ttu-id="4491e-107">応答側プライベート プロセスは、応答側の内部ビジネス プロセスです。</span><span class="sxs-lookup"><span data-stu-id="4491e-107">The responder private process is the business process that is internal to the responder.</span></span> <span data-ttu-id="4491e-108">このプライベート プロセスにより、応答側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。</span><span class="sxs-lookup"><span data-stu-id="4491e-108">The private process provides back-end integration between the responder public process and the back-end line-of-business program.</span></span> <span data-ttu-id="4491e-109">応答側プライベート プロセスは、パブリック プロセスと通信してメッセージに応答します。</span><span class="sxs-lookup"><span data-stu-id="4491e-109">The responder private process communicates with the public process to respond to messages.</span></span>  
  
 <span data-ttu-id="4491e-110">応答側プライベート プロセスは実装ごとに固有です。</span><span class="sxs-lookup"><span data-stu-id="4491e-110">The responder private process is unique for each implementation.</span></span> <span data-ttu-id="4491e-111">PrivateResponder.odx サンプルは用途に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4491e-111">You can customize the PrivateResponder.odx sample for your purposes.</span></span> <span data-ttu-id="4491e-112">ただし、応答側パブリック プロセスの機能に支障をきたさないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4491e-112">You must be careful that you do not adversely affect the functioning of the responder public process.</span></span>  
  
 <span data-ttu-id="4491e-113">詳細については、メッセージ フローの説明を含む、次を参照してください。[応答側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)します。</span><span class="sxs-lookup"><span data-stu-id="4491e-113">For more information, including a description of the message flow, see [Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4491e-114">参照</span><span class="sxs-lookup"><span data-stu-id="4491e-114">See Also</span></span>  
 <span data-ttu-id="4491e-115">[オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="4491e-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="4491e-116">プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="4491e-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)