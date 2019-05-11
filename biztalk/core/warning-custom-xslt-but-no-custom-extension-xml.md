---
title: 警告 - カスタム xslt は上書きがないカスタム拡張 XML |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.customXsltButNoCustomExtensionXML
ms.assetid: af008ac2-e9ae-4753-a5ba-bf4dbb711a4e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4c44fbe8385717061be1e5d8e81587d6a287b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393710"
---
# <a name="warning---custom-xslt-but-no-custom-extension-xml"></a><span data-ttu-id="5d5c0-102">警告 - カスタム xslt は上書きがないカスタム拡張 XML</span><span class="sxs-lookup"><span data-stu-id="5d5c0-102">Warning - Custom XSLT but No Custom Extension XML</span></span>
<span data-ttu-id="5d5c0-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="5d5c0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="5d5c0-104">btm1034</span><span class="sxs-lookup"><span data-stu-id="5d5c0-104">btm1034</span></span>  
  
 <span data-ttu-id="5d5c0-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="5d5c0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="5d5c0-106">**カスタム XSLT パス**プロパティが上書きされましたが、**カスタム拡張 XML**オーバーライドされるプロパティ。</span><span class="sxs-lookup"><span data-stu-id="5d5c0-106">The **Custom XSLT Path** property has been overridden without the **Custom Extension XML** property being overridden.</span></span> <span data-ttu-id="5d5c0-107">これが意図的な場合は、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="5d5c0-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="5d5c0-108">BizTalk マッパーがで指定された XSLT を使用して、**カスタム XSLT パス**プロパティと、ダミーの拡張 XML マッピング ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="5d5c0-108">BizTalk Mapper will use the XSLT specified by the **Custom XSLT Path** property and generate a dummy Extension XML mapping file.</span></span> <span data-ttu-id="5d5c0-109">指定されたカスタム XSLT 内から外部アセンブリへの呼び出しを行った場合を使用してファイルを指定する必要があります、**カスタム拡張 XML**アセンブリ名マップのプレフィックスを格納するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="5d5c0-109">If you make calls to external assemblies from within the provided custom XSLT, you must specify a file using the **Custom Extension XML** property that contains the prefix to assembly name mapping.</span></span>  
  
 <span data-ttu-id="5d5c0-110">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="5d5c0-110">**User Action**</span></span>  
  
 <span data-ttu-id="5d5c0-111">値を設定するかこの警告で報告された状態が意図的でない場合、**カスタム拡張 XML**上書きした値にプロパティまたは削除、**カスタム XSLT パス**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="5d5c0-111">If the condition indicated by this warning was not intentional, either provide a compatible value for the **Custom Extension XML** property or remove the override value for the **Custom XSLT Path** property.</span></span>