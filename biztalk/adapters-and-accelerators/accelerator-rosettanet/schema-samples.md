---
title: スキーマのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2d5397319bcf7472a0999adcfc64fd7519d10c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008411"
---
# <a name="schema-samples"></a><span data-ttu-id="3252b-102">スキーマのサンプル</span><span class="sxs-lookup"><span data-stu-id="3252b-102">Schema Samples</span></span>
<span data-ttu-id="3252b-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK には、一連 RNIF と PIP Partner Interface Process () の処理のための XSD スキーマにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3252b-103">The Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK includes a series of XSD schemas for RNIF and Partner Interface Process (PIP) processing.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3252b-104"> これらのスキーマを使用して、メッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="3252b-104"> uses these schemas to process messages.</span></span> <span data-ttu-id="3252b-105">これらのスキーマは目的に応じて変更したり、エラーのトラブルシューティングに使用したりできます。</span><span class="sxs-lookup"><span data-stu-id="3252b-105">You can modify these schemas for your own purposes, or use these to troubleshoot failures.</span></span>  
  
 <span data-ttu-id="3252b-106">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK にはスキーマが 3 セット用意されています。</span><span class="sxs-lookup"><span data-stu-id="3252b-106">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK provides three sets of schemas.</span></span> <span data-ttu-id="3252b-107">これらのスキーマは、RosettaNet の PIP、RosettaNet の次世代スキーマ、および RNIF スキーマに関連付けられた XSD スキーマです。</span><span class="sxs-lookup"><span data-stu-id="3252b-107">These schemas are XSD schemas associated with RosettaNet PIPs, RosettaNet next-generation schemas, and RNIF schemas.</span></span>  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a><span data-ttu-id="3252b-108">RosettaNet PIP に関連付けられた XSD スキーマ</span><span class="sxs-lookup"><span data-stu-id="3252b-108">XSD Schemas associated with RosettaNet PIPs</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3252b-109"> では、これらのスキーマを使用して、メッセージ インスタンスのサービス コンテンツを検証します。</span><span class="sxs-lookup"><span data-stu-id="3252b-109"> uses these schemas to validate the service content of message instances.</span></span> <span data-ttu-id="3252b-110">これらのスキーマを変更してメッセージの処理方法を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="3252b-110">You can modify these schemas to change message processing.</span></span> <span data-ttu-id="3252b-111">また、サービス コンテンツの処理中にエラーが発生した場合は、これらのスキーマを使用してメッセージを検証し、原因を突き止めることができます。</span><span class="sxs-lookup"><span data-stu-id="3252b-111">You can also use the schemas to validate message instances when troubleshooting errors in processing service content.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3252b-112"> では、これらのスキーマが RNPIP アセンブリにコンパイルされています。</span><span class="sxs-lookup"><span data-stu-id="3252b-112"> has compiled these schemas into the RNPIPs assembly.</span></span> <span data-ttu-id="3252b-113">これらのスキーマのいずれかを変更する場合は、RNPIP アセンブリの展開を解除し、スキーマを変更してから RNPIP を再度展開します。</span><span class="sxs-lookup"><span data-stu-id="3252b-113">You can modify any one of these schemas by undeploying the RNPIPs assembly, changing the schema, and then redeploying RNPIPs.</span></span> <span data-ttu-id="3252b-114">スキーマを変更しないように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3252b-114">You must be careful that you do not change the schema.</span></span> <span data-ttu-id="3252b-115">スキーマを変更すると、対応する RosettaNet PIP に対応しなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3252b-115">If you change the schema, your changes may not comply with the corresponding RosettaNet PIP.</span></span> <span data-ttu-id="3252b-116">スキーマを RNPIP に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="3252b-116">You can also add a schema to RNPIPs.</span></span> <span data-ttu-id="3252b-117">詳細については、次を参照してください。 [Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)します。</span><span class="sxs-lookup"><span data-stu-id="3252b-117">For more information, see [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="3252b-118">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってこれらのスキーマ\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK\Schemas します。</span><span class="sxs-lookup"><span data-stu-id="3252b-118">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span>  
  
## <a name="rnif-schemas"></a><span data-ttu-id="3252b-119">RNIF のスキーマ</span><span class="sxs-lookup"><span data-stu-id="3252b-119">RNIF Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3252b-120"> はこれらのスキーマを使用して、Preamble、Service Header、Delivery Header などの RNIF メッセージの構成要素を検証します。</span><span class="sxs-lookup"><span data-stu-id="3252b-120"> uses these schemas to validate RNIF message parts, such as the preamble, service header, and delivery header.</span></span> <span data-ttu-id="3252b-121">また、これらには受信確認と例外のスキーマも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3252b-121">These also include schemas for acknowledgments and exceptions.</span></span>  
  
 <span data-ttu-id="3252b-122">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってこれらのスキーマ\<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK\RNIFSchemas します。</span><span class="sxs-lookup"><span data-stu-id="3252b-122">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\RNIFSchemas.</span></span>  
  
## <a name="rosettanet-next-generation-schemas"></a><span data-ttu-id="3252b-123">RosettaNet の次世代スキーマ</span><span class="sxs-lookup"><span data-stu-id="3252b-123">RosettaNet Next-Generation Schemas</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3252b-124"> はこれらのスキーマを使用して、メッセージが RosettaNet の次世代スキーマに準拠しているかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="3252b-124"> uses these schemas to validate messages conforming to next-generation schemas for RosettaNet.</span></span> <span data-ttu-id="3252b-125">これらのスキーマは、DTD ではなく XSD をネイティブでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3252b-125">These schemas support XSD natively, instead of DTDs.</span></span> <span data-ttu-id="3252b-126">これらのスキーマを使用する追加 Rnpip アセンブリに」の説明に従って[Rnpip の既存の PIP 変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)します。</span><span class="sxs-lookup"><span data-stu-id="3252b-126">To use these schemas, add them to the RNPIPs assembly as described in [Modifying an Existing PIP in RNPIPs](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).</span></span>  
  
 <span data-ttu-id="3252b-127">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]セットアップ プログラムによってこれらのスキーマ、 \<*ドライブ*\>: \Program Files\\Microsoft BizTalk\<バージョン\>のアクセラレータRosettanet \sdk\schemas の \domain、\Interchange、および \Universal フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3252b-127">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Setup program installs these schemas in the \<*drive*\>:\Program Files\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas\Domain, \Interchange, and \Universal folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3252b-128">参照</span><span class="sxs-lookup"><span data-stu-id="3252b-128">See Also</span></span>  
 <span data-ttu-id="3252b-129">[PIP 実装](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span><span class="sxs-lookup"><span data-stu-id="3252b-129">[PIP Implementation](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md) </span></span>  
 <span data-ttu-id="3252b-130">[Pip の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span><span class="sxs-lookup"><span data-stu-id="3252b-130">[Working with PIPs](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md) </span></span>  
 [<span data-ttu-id="3252b-131">サンプル</span><span class="sxs-lookup"><span data-stu-id="3252b-131">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)