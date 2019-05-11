---
title: 警告 - カスタム拡張 XML がないカスタム xslt は上書き |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customExtensionXmlButNoCustomXSLT
ms.assetid: 3219c73c-2e58-4fe2-bc6e-2d60348d2415
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d94bea29ee6943ee6b084518e4b4ff404377503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393727"
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a><span data-ttu-id="e26c1-102">警告 - カスタム拡張 XML がないカスタム xslt は上書き</span><span class="sxs-lookup"><span data-stu-id="e26c1-102">Warning - Custom Extension XML But No Custom XSLT</span></span>
<span data-ttu-id="e26c1-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="e26c1-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e26c1-104">btm1033</span><span class="sxs-lookup"><span data-stu-id="e26c1-104">btm1033</span></span>  
  
 <span data-ttu-id="e26c1-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="e26c1-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e26c1-106">**カスタム拡張 XML**プロパティが上書きされましたが、**カスタム XSLT パス**オーバーライドされるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e26c1-106">The **Custom Extension XML** property has been overridden without the **Custom XSLT Path** property being overridden.</span></span> <span data-ttu-id="e26c1-107">これが意図的な場合は、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="e26c1-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="e26c1-108">BizTalk マッパーは、マップのコンパイルによって生成された XSLT を使用してとはも拡張 XML を生成し、オーバーライドされたプロパティで指定されたカスタム拡張 XML に追加します。</span><span class="sxs-lookup"><span data-stu-id="e26c1-108">BizTalk Mapper will use the XSLT produced by compiling the map and will also generate the Extension XML and append it to the custom Extension XML specified by the overridden property.</span></span> <span data-ttu-id="e26c1-109">これは、便利な場合、マップが含まれています**Scripting**インライン XSLT またはインライン XSLT を使用して、functoid が外部アセンブリ内の 1 つまたは複数のメソッドの呼び出しを構成するテンプレートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e26c1-109">This can be useful when the map contains **Scripting** functoids that use inline XSLT or inline XSLT call templates that make calls to one or more methods in external assemblies.</span></span> <span data-ttu-id="e26c1-110">このような場合、ユーザーでアセンブリ名マップにプレフィックスを指定、**カスタム拡張 XML**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e26c1-110">In such cases, the user can then specify the prefix to assembly name mapping in the **Custom Extension XML** property.</span></span>  
  
 <span data-ttu-id="e26c1-111">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="e26c1-111">**User Action**</span></span>  
  
 <span data-ttu-id="e26c1-112">値を設定するかこの警告で報告された状態が意図的でない場合、**カスタム XSLT パス**上書きした値にプロパティまたは削除、**カスタム拡張 XML**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e26c1-112">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom XSLT Path** property or remove the override value for the **Custom Extension XML** property.</span></span>