---
title: '手順 6: スキーマの検証 |Microsoft ドキュメント'
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
ms.openlocfilehash: b6de54e086865f0ca6c406ad8c24127192c8353f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206338"
---
# <a name="step-6-validate-the-schemas"></a><span data-ttu-id="efecd-102">手順 6: スキーマを検証します。</span><span class="sxs-lookup"><span data-stu-id="efecd-102">Step 6: Validate the Schemas</span></span>
<span data-ttu-id="efecd-103">このステップでは、検証スキーマ コマンドを使用する、スキーマのいずれか、内部不整合があるかからインスタンス メッセージの処理を効果的に使用されているいずれかのスキーマを妨げる可能性のあるその他の問題があるかを確認します。</span><span class="sxs-lookup"><span data-stu-id="efecd-103">In this step, you use the validate schema command to determine if either of the schemas contains any internal inconsistencies, or has other issues that might prevent either schema from being used effectively for processing instance messages.</span></span>  
  
### <a name="to-validate-the-schema"></a><span data-ttu-id="efecd-104">スキーマを検証するには</span><span class="sxs-lookup"><span data-stu-id="efecd-104">To validate the schema</span></span>  
  
1.  <span data-ttu-id="efecd-105">ソリューション エクスプ ローラーで右クリック**Doorbell.xsd**  をクリックし、**スキーマの検証**です。</span><span class="sxs-lookup"><span data-stu-id="efecd-105">In Solution Explorer, right-click **Doorbell.xsd** and then click **Validate Schema**.</span></span> <span data-ttu-id="efecd-106">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efecd-106">Ensure that a success message appears in the output window.</span></span>  
  
     <span data-ttu-id="efecd-107">成功メッセージが表示されない場合は、作成されていることを確認してください。 **Doorbell.xsd**適切です。</span><span class="sxs-lookup"><span data-stu-id="efecd-107">If a success message does not appear, verify that you created **Doorbell.xsd** properly.</span></span>  
  
2.  <span data-ttu-id="efecd-108">ステップ 1 を繰り返します、 **ADT_A04_22_GLO_DEF.xsd**スキーマ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="efecd-108">Repeat step 1 for the **ADT_A04_22_GLO_DEF.xsd** schema file.</span></span> <span data-ttu-id="efecd-109">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="efecd-109">Ensure that a success message appears in the output window.</span></span>  
  
 <span data-ttu-id="efecd-110">進みます[手順 7: サインインし、プロジェクトをビルド](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)です。</span><span class="sxs-lookup"><span data-stu-id="efecd-110">Proceed to [Step 7: Sign and Build the Projects](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efecd-111">参照</span><span class="sxs-lookup"><span data-stu-id="efecd-111">See Also</span></span>  
 [<span data-ttu-id="efecd-112">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="efecd-112">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)