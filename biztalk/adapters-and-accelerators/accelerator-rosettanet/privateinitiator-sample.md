---
title: PrivateInitiator サンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f176566-2a71-487d-84c1-5e7767701e8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ab84d145939191a8bdbca9afb44d04fdf24b3e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011283"
---
# <a name="privateinitiator-sample"></a><span data-ttu-id="dde4c-102">PrivateInitiator サンプル</span><span class="sxs-lookup"><span data-stu-id="dde4c-102">PrivateInitiator Sample</span></span>
<span data-ttu-id="dde4c-103">PrivateInitiator.odx サンプルには、Microsoft® BizTalk Server によってインストールされる開始側プライベート プロセスのコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dde4c-103">The PrivateInitiator.odx sample contains the code for the initiator private process installed by Microsoft® BizTalk Server.</span></span> <span data-ttu-id="dde4c-104">これは、SQL アダプターベースの既定の送受信ポートを使用して RNIF Service Content メッセージを送受信する、汎用のプライベート プロセスです。</span><span class="sxs-lookup"><span data-stu-id="dde4c-104">This is a generic private process that sends and receives RNIF service-content messages from the default SQL adapter-based send and receive ports.</span></span>  
  
 <span data-ttu-id="dde4c-105">既定で、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってサンプルでは、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>のアクセラレータRosettaNet\SDK\PrivateInitiator します。</span><span class="sxs-lookup"><span data-stu-id="dde4c-105">By default, the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs the sample in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\PrivateInitiator.</span></span>  
  
## <a name="sample-contents"></a><span data-ttu-id="dde4c-106">サンプルの内容</span><span class="sxs-lookup"><span data-stu-id="dde4c-106">Sample Contents</span></span>  
 <span data-ttu-id="dde4c-107">開始側プライベート プロセスは、開始側の内部ビジネス プロセスです。</span><span class="sxs-lookup"><span data-stu-id="dde4c-107">The initiator private process is the business process that is internal to the initiator.</span></span> <span data-ttu-id="dde4c-108">このプライベート プロセスにより、開始側パブリック プロセスとバックエンド基幹業務プログラムとの間にバックエンド統合がもたらされます。</span><span class="sxs-lookup"><span data-stu-id="dde4c-108">The private process provides back-end integration between the initiator public process and the back-end line-of-business program.</span></span> <span data-ttu-id="dde4c-109">開始側プライベート プロセスは、パブリック プロセスと通信してメッセージを開始します。</span><span class="sxs-lookup"><span data-stu-id="dde4c-109">The initiator private process communicates with the public process to initiate messages.</span></span>  
  
 <span data-ttu-id="dde4c-110">開始側プライベート プロセスは実装ごとに固有です。</span><span class="sxs-lookup"><span data-stu-id="dde4c-110">The initiator private process is unique for each implementation.</span></span> <span data-ttu-id="dde4c-111">PrivateInitiator.odx サンプルは用途に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="dde4c-111">You can customize the PrivateInitiator.odx sample for your purposes.</span></span> <span data-ttu-id="dde4c-112">ただし、開始側パブリック プロセスの機能に支障をきたさないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dde4c-112">You must be careful that you do not adversely affect the functioning of the initiator public process.</span></span>  
  
 <span data-ttu-id="dde4c-113">詳細については、メッセージ フローの説明を含む、[開始側プライベート プロセス](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dde4c-113">For more information, including a description of the message flow, see [Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde4c-114">参照</span><span class="sxs-lookup"><span data-stu-id="dde4c-114">See Also</span></span>  
 <span data-ttu-id="dde4c-115">[オーケストレーション サンプル](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="dde4c-115">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="dde4c-116">プライベート プロセス</span><span class="sxs-lookup"><span data-stu-id="dde4c-116">Private Processes</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)