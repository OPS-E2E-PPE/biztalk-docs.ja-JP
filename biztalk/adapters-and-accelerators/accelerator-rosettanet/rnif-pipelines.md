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
ms.openlocfilehash: 458eeed6643aa6f8ea5211f517b33a6886d3e756
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282354"
---
# <a name="rnif-pipelines"></a><span data-ttu-id="d393b-102">RNIF パイプライン</span><span class="sxs-lookup"><span data-stu-id="d393b-102">RNIF Pipelines</span></span>
<span data-ttu-id="d393b-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]受信および送信パイプラインが受信に必要な処理を実行または RosettaNet Implementation Framework (RNIF) メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="d393b-103">The Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] receive and send pipelines perform the processing required for receive or send RosettaNet Implementation Framework (RNIF) messages.</span></span> <span data-ttu-id="d393b-104">この処理には、前処理、デコード、エンコード、暗号化/復号化、逆アセンブルとアセンブル、およびパーティの認証が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d393b-104">This processing includes preprocessing, decoding/encoding, decrypting/encrypting, disassembly/assembly, and party authentication.</span></span>  
  
## <a name="pipeline-files"></a><span data-ttu-id="d393b-105">パイプライン ファイル</span><span class="sxs-lookup"><span data-stu-id="d393b-105">Pipeline Files</span></span>  
 <span data-ttu-id="d393b-106">標準[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]受信し、送信パイプラインがネイティブに RNIF メッセージを処理しない操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d393b-106">Standard [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] receive and send pipelines do not process RNIF messages natively.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] <span data-ttu-id="d393b-107">追加のカスタム受信および送信パイプラインをこの目的のためです。</span><span class="sxs-lookup"><span data-stu-id="d393b-107">has added custom receive and send pipelines for this purpose.</span></span> <span data-ttu-id="d393b-108">これらのパイプラインは上に構築された、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]パイプラインが追加[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-特定の処理機能。</span><span class="sxs-lookup"><span data-stu-id="d393b-108">These pipelines are built on the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] pipelines, but add [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]-specific processing capability.</span></span> <span data-ttu-id="d393b-109">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン (RNIFReceive.btp および RNIFSend.btp) で使用可能な[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK \<*ドライブ*\>: \Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\rnpipelines にあります。</span><span class="sxs-lookup"><span data-stu-id="d393b-109">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] pipelines (RNIFReceive.btp and RNIFSend.btp) are available in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK at \<*drive*\>:\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\RNPipelines.</span></span> <span data-ttu-id="d393b-110">これにより、独自の目的に合わせてカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="d393b-110">This lets you customize them for your own purposes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d393b-111">参照</span><span class="sxs-lookup"><span data-stu-id="d393b-111">See Also</span></span>  
 <span data-ttu-id="d393b-112">[BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="d393b-112">[BTARN Receive Pipeline](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md) </span></span>  
 [<span data-ttu-id="d393b-113">BTARN 送信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d393b-113">BTARN Send Pipeline</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)