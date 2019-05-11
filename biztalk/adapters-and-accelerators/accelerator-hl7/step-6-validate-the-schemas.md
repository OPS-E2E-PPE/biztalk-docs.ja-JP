---
title: 手順 6:スキーマの検証 |Microsoft Docs
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
ms.openlocfilehash: 43e22b3dfafd242305105fba14e6c8441f568bb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287943"
---
# <a name="step-6-validate-the-schemas"></a><span data-ttu-id="3ce47-102">手順 6:スキーマを検証します。</span><span class="sxs-lookup"><span data-stu-id="3ce47-102">Step 6: Validate the Schemas</span></span>
<span data-ttu-id="3ce47-103">この手順では、検証のスキーマ コマンドを使用する、スキーマのいずれか、内部の不整合が含まれていますかからインスタンス メッセージを処理するために効果的に使用されているいずれかのスキーマを妨げる可能性のあるその他の問題があるかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3ce47-103">In this step, you use the validate schema command to determine if either of the schemas contains any internal inconsistencies, or has other issues that might prevent either schema from being used effectively for processing instance messages.</span></span>  
  
### <a name="to-validate-the-schema"></a><span data-ttu-id="3ce47-104">スキーマを検証するには</span><span class="sxs-lookup"><span data-stu-id="3ce47-104">To validate the schema</span></span>  
  
1. <span data-ttu-id="3ce47-105">ソリューション エクスプ ローラーで右クリックして**Doorbell.xsd**し**スキーマの検証**です。</span><span class="sxs-lookup"><span data-stu-id="3ce47-105">In Solution Explorer, right-click **Doorbell.xsd** and then click **Validate Schema**.</span></span> <span data-ttu-id="3ce47-106">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ce47-106">Ensure that a success message appears in the output window.</span></span>  
  
    <span data-ttu-id="3ce47-107">成功メッセージが表示されない場合は、作成したことを確認**Doorbell.xsd**適切です。</span><span class="sxs-lookup"><span data-stu-id="3ce47-107">If a success message does not appear, verify that you created **Doorbell.xsd** properly.</span></span>  
  
2. <span data-ttu-id="3ce47-108">ステップ 1 を繰り返します、 **ADT_A04_22_GLO_DEF.xsd**スキーマ ファイル。</span><span class="sxs-lookup"><span data-stu-id="3ce47-108">Repeat step 1 for the **ADT_A04_22_GLO_DEF.xsd** schema file.</span></span> <span data-ttu-id="3ce47-109">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ce47-109">Ensure that a success message appears in the output window.</span></span>  
  
   <span data-ttu-id="3ce47-110">続行する[手順 7。サインインし、プロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)します。</span><span class="sxs-lookup"><span data-stu-id="3ce47-110">Proceed to [Step 7: Sign and Build the Projects](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce47-111">参照</span><span class="sxs-lookup"><span data-stu-id="3ce47-111">See Also</span></span>  
 [<span data-ttu-id="3ce47-112">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="3ce47-112">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)