---
title: RNIF パイプライン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RNIF, pipelines
- pipelines, RNIF
ms.assetid: 6cf480fe-6b54-4b13-8318-617f3bba71d0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9245517e9a333229912e6c18c3a48ea06eadf50a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988499"
---
# <a name="rnif-pipelines"></a><span data-ttu-id="8c224-102">RNIF パイプライン</span><span class="sxs-lookup"><span data-stu-id="8c224-102">RNIF Pipelines</span></span>
<span data-ttu-id="8c224-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信および送信パイプラインが受信に必要な処理を実行または RosettaNet Implementation Framework (RNIF) メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="8c224-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive and send pipelines perform the processing required for receive or send RosettaNet Implementation Framework (RNIF) messages.</span></span> <span data-ttu-id="8c224-104">この処理には、事前処理、デコードとエンコード、暗号化の解除と暗号化、逆アセンブルとアセンブル、およびパーティ認証が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c224-104">This processing includes preprocessing, decoding/encoding, decrypting/encrypting, disassembly/assembly, and party authentication.</span></span>  
  
## <a name="pipeline-files"></a><span data-ttu-id="8c224-105">パイプライン ファイル</span><span class="sxs-lookup"><span data-stu-id="8c224-105">Pipeline Files</span></span>  
 <span data-ttu-id="8c224-106">標準[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信し、送信パイプラインがネイティブに RNIF メッセージを処理しない操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8c224-106">Standard [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive and send pipelines do not process RNIF messages natively.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="8c224-107"> 追加のカスタム受信および送信パイプラインをこの目的のためです。</span><span class="sxs-lookup"><span data-stu-id="8c224-107"> has added custom receive and send pipelines for this purpose.</span></span> <span data-ttu-id="8c224-108">これらのパイプラインは [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] パイプライン上に構築されていますが、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 固有の処理機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="8c224-108">These pipelines are built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] pipelines, but add [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-specific processing capability.</span></span> <span data-ttu-id="8c224-109">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン (RNIFReceive.btp および RNIFSend.btp) で使用可能な[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK \<*ドライブ*\>: \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。</span><span class="sxs-lookup"><span data-stu-id="8c224-109">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipelines (RNIFReceive.btp and RNIFSend.btp) are available in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK at \<*drive*\>:\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="8c224-110">これによって、独自の目的に合わせたパイプラインのカスタマイズが可能になります。</span><span class="sxs-lookup"><span data-stu-id="8c224-110">This lets you customize them for your own purposes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c224-111">参照</span><span class="sxs-lookup"><span data-stu-id="8c224-111">See Also</span></span>  
 <span data-ttu-id="8c224-112">[BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="8c224-112">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="8c224-113">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="8c224-113">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)