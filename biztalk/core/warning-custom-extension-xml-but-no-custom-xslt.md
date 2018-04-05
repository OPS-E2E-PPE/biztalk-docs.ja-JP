---
title: 警告 - カスタム拡張 XML がないカスタム xslt は上書き |Microsoft ドキュメント
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
ms.openlocfilehash: 8b626f8ede3231c04ae74dc0097cbdf524c90522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="warning---custom-extension-xml-but-no-custom-xslt"></a><span data-ttu-id="543ca-102">警告 - カスタム拡張 XML がないカスタム xslt は上書き</span><span class="sxs-lookup"><span data-stu-id="543ca-102">Warning - Custom Extension XML But No Custom XSLT</span></span>
<span data-ttu-id="543ca-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="543ca-103">**Error Code**</span></span>  
  
 <span data-ttu-id="543ca-104">btm1033</span><span class="sxs-lookup"><span data-stu-id="543ca-104">btm1033</span></span>  
  
 <span data-ttu-id="543ca-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="543ca-105">**Explanation**</span></span>  
  
 <span data-ttu-id="543ca-106">**カスタム拡張 XML**プロパティが上書きされましたが、**カスタム XSLT パス**オーバーライドされるプロパティです。</span><span class="sxs-lookup"><span data-stu-id="543ca-106">The **Custom Extension XML** property has been overridden without the **Custom XSLT Path** property being overridden.</span></span> <span data-ttu-id="543ca-107">これを意図的に行っている場合は、この警告を無視してください。</span><span class="sxs-lookup"><span data-stu-id="543ca-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="543ca-108">BizTalk マッパーは、マップをコンパイルして作成された XSLT を使用します。また、拡張 XML を生成して、上書き先のプロパティで指定されているカスタム拡張 XML に追加します。</span><span class="sxs-lookup"><span data-stu-id="543ca-108">BizTalk Mapper will use the XSLT produced by compiling the map and will also generate the Extension XML and append it to the custom Extension XML specified by the overridden property.</span></span> <span data-ttu-id="543ca-109">これを利用する、マップが含まれている**スクリプト**インライン XSLT またはインライン XSLT を使用する functoid を呼び出す外部アセンブリの 1 つまたは複数のメソッドの呼び出しを構成するテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="543ca-109">This can be useful when the map contains **Scripting** functoids that use inline XSLT or inline XSLT call templates that make calls to one or more methods in external assemblies.</span></span> <span data-ttu-id="543ca-110">このような場合、ユーザーでアセンブリ名マップにプレフィックスを指定、**カスタム拡張 XML**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="543ca-110">In such cases, the user can then specify the prefix to assembly name mapping in the **Custom Extension XML** property.</span></span>  
  
 <span data-ttu-id="543ca-111">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="543ca-111">**User Action**</span></span>  
  
 <span data-ttu-id="543ca-112">互換性のある値を設定するか場合、この警告で報告された状態が意図しないもので、**カスタム XSLT パス**上書きした値をプロパティ、または削除、**カスタム拡張 XML**プロパティです。</span><span class="sxs-lookup"><span data-stu-id="543ca-112">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom XSLT Path** property or remove the override value for the **Custom Extension XML** property.</span></span>