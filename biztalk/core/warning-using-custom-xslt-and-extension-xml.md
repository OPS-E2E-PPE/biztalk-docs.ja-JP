---
title: 警告 - カスタム XSLT およびカスタム拡張 XML を使用して |Microsoft ドキュメント
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
ms.openlocfilehash: 90644aec738345e3a36286cc62aaa7a355e04348
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288586"
---
# <a name="warning---using-custom-xslt-and-extension-xml"></a><span data-ttu-id="8bfc3-102">警告 - カスタム XSLT およびカスタム拡張 XML を使用します。</span><span class="sxs-lookup"><span data-stu-id="8bfc3-102">Warning - Using Custom XSLT and Extension XML</span></span>
<span data-ttu-id="8bfc3-103">**エラー コード**</span><span class="sxs-lookup"><span data-stu-id="8bfc3-103">**Error Code**</span></span>  
  
 <span data-ttu-id="8bfc3-104">btm1035</span><span class="sxs-lookup"><span data-stu-id="8bfc3-104">btm1035</span></span>  
  
 <span data-ttu-id="8bfc3-105">**説明**</span><span class="sxs-lookup"><span data-stu-id="8bfc3-105">**Explanation**</span></span>  
  
 <span data-ttu-id="8bfc3-106">上書きの存在の値を**カスタム XSLT パス**と**カスタム拡張 XML**プロパティがすべてのマッピングを完全に無視して、このマップによって生成された出力インスタンス メッセージを制御します。送信元と送信先スキーマ間で指定します。</span><span class="sxs-lookup"><span data-stu-id="8bfc3-106">The presence of override values for the **Custom XSLT Path** and **Custom Extension XML** properties is controlling the output instance messages produced by this map, completely ignoring any mappings specified between the source and destination schemas.</span></span> <span data-ttu-id="8bfc3-107">これを意図的に行っている場合は、この警告を無視してください。</span><span class="sxs-lookup"><span data-stu-id="8bfc3-107">If this is intentional, you can ignore this warning.</span></span>  
  
 <span data-ttu-id="8bfc3-108">これが有効で 1 つのシナリオは BizTalk マッパーを使用してマッピング用の一次 XSLT を生成、固有の追加要件を満たすには、手動でこの XSLT を変更し、値に変更したファイルを指定する、**カスタム XSLT パス**プロパティ、後続のマッピング操作中に、一次 XSLT は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="8bfc3-108">One scenario in which this is valid is to use BizTalk Mapper to generate preliminary XSLT for the mapping, modify this XSLT by hand to meet specific additional requirements, and then specify the modified file as the value of the **Custom XSLT Path** property, thereby overriding the preliminary XSLT during subsequent mapping operations.</span></span>  
  
 <span data-ttu-id="8bfc3-109">**ユーザーの操作**</span><span class="sxs-lookup"><span data-stu-id="8bfc3-109">**User Action**</span></span>  
  
 <span data-ttu-id="8bfc3-110">このマップ内で指定されたマッピングを上書きする予定がない場合は、上書き値を削除する、**カスタム XSLT パス**プロパティおよび**カスタム拡張 XML**に応じてのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="8bfc3-110">If you do not intend to override the mapping specified within this map, remove the override values for the **Custom XSLT Path** property and the **Custom Extension XML** property, as appropriate.</span></span>