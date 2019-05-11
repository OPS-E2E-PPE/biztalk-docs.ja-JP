---
title: 警告 - カスタム XSLT およびカスタム拡張 XML を使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.warning.usingCustomXsltAndExtensionXML
ms.assetid: b86da5fb-6435-4e3b-89b6-d9d036b5152b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce44d40fd726731261536b622fdb9b24c65f4281
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393641"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a><span data-ttu-id="cf935-102">警告 - カスタム XSLT およびカスタム拡張 XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf935-102">Warning - Using Custom XSLT and Extension XML</span></span>
<span data-ttu-id="cf935-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="cf935-103">**Error Code**</span></span>  
  
 <span data-ttu-id="cf935-104">btm1035</span><span class="sxs-lookup"><span data-stu-id="cf935-104">btm1035</span></span>  
  
 <span data-ttu-id="cf935-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="cf935-105">**Explanation**</span></span>  
  
 <span data-ttu-id="cf935-106">上書きのプレゼンスの値を**カスタム XSLT パス**と**カスタム拡張 XML**プロパティがすべてのマッピングを完全に無視します、このマップによって生成された出力インスタンス メッセージを制御します。元と送信先スキーマの間に指定します。</span><span class="sxs-lookup"><span data-stu-id="cf935-106">The presence of override values for the **Custom XSLT Path** and **Custom Extension XML** properties is controlling the output instance messages produced by this map, completely ignoring any mappings specified between the source and destination schemas.</span></span> <span data-ttu-id="cf935-107">これが意図的な場合は、この警告を無視できます。</span><span class="sxs-lookup"><span data-stu-id="cf935-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="cf935-108">これが有効な 1 つのシナリオが BizTalk マッパーを使用して、マッピング用の一次 XSLT を生成する、特定の追加要件を満たすには、手動でこの XSLT を変更およびの値として、変更されたファイルを指定するには、**カスタム XSLT パス**プロパティ、後続のマッピング操作中に、一次 XSLT は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="cf935-108">One scenario in which this is valid is to use BizTalk Mapper to generate preliminary XSLT for the mapping, modify this XSLT by hand to meet specific additional requirements, and then specify the modified file as the value of the **Custom XSLT Path** property, thereby overriding the preliminary XSLT during subsequent mapping operations.</span></span>  
  
 <span data-ttu-id="cf935-109">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="cf935-109">**User Action**</span></span>  
  
 <span data-ttu-id="cf935-110">このマップ内で指定されたマッピングを上書きしない場合は、上書き値を削除、**カスタム XSLT パス**プロパティおよび**カスタム拡張 XML**適切なプロパティ。</span><span class="sxs-lookup"><span data-stu-id="cf935-110">If you do not intend to override the mapping specified within this map, remove the override values for the **Custom XSLT Path** property and the **Custom Extension XML** property, as appropriate.</span></span>