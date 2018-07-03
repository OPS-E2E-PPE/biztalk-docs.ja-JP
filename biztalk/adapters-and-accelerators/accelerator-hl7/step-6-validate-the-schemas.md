---
title: '手順 6: スキーマの検証 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- schemas, validating
- validating, schemas
ms.assetid: 58cd8680-d135-485a-9463-e7701202eaf7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94f0ab3ba2d9586aa60817bb261be0660305c820
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005339"
---
# <a name="step-6-validate-the-schemas"></a><span data-ttu-id="29b19-102">手順 6: スキーマを検証します。</span><span class="sxs-lookup"><span data-stu-id="29b19-102">Step 6: Validate the Schemas</span></span>
<span data-ttu-id="29b19-103">この手順では、検証のスキーマ コマンドを使用する、スキーマのいずれか、内部の不整合が含まれていますかからインスタンス メッセージを処理するために効果的に使用されているいずれかのスキーマを妨げる可能性のあるその他の問題があるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="29b19-103">In this step, you use the validate schema command to determine if either of the schemas contains any internal inconsistencies, or has other issues that might prevent either schema from being used effectively for processing instance messages.</span></span>  
  
### <a name="to-validate-the-schema"></a><span data-ttu-id="29b19-104">スキーマを検証するには</span><span class="sxs-lookup"><span data-stu-id="29b19-104">To validate the schema</span></span>  
  
1. <span data-ttu-id="29b19-105">ソリューション エクスプ ローラーで右クリックして**Doorbell.xsd**し**スキーマの検証**です。</span><span class="sxs-lookup"><span data-stu-id="29b19-105">In Solution Explorer, right-click **Doorbell.xsd** and then click **Validate Schema**.</span></span> <span data-ttu-id="29b19-106">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29b19-106">Ensure that a success message appears in the output window.</span></span>  
  
    <span data-ttu-id="29b19-107">成功メッセージが表示されない場合は、作成したことを確認**Doorbell.xsd**適切です。</span><span class="sxs-lookup"><span data-stu-id="29b19-107">If a success message does not appear, verify that you created **Doorbell.xsd** properly.</span></span>  
  
2. <span data-ttu-id="29b19-108">ステップ 1 を繰り返します、 **ADT_A04_22_GLO_DEF.xsd**スキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="29b19-108">Repeat step 1 for the **ADT_A04_22_GLO_DEF.xsd** schema file.</span></span> <span data-ttu-id="29b19-109">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29b19-109">Ensure that a success message appears in the output window.</span></span>  
  
   <span data-ttu-id="29b19-110">進みます[手順 7: サインインし、プロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="29b19-110">Proceed to [Step 7: Sign and Build the Projects](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29b19-111">参照</span><span class="sxs-lookup"><span data-stu-id="29b19-111">See Also</span></span>  
 [<span data-ttu-id="29b19-112">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="29b19-112">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)