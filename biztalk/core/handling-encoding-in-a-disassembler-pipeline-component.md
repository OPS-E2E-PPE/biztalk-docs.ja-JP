---
title: 逆アセンブラー パイプライン コンポーネントでのエンコードの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], encoding
- pipeline components [custom], disassembling
ms.assetid: 33420357-421f-4ad0-8eee-d445376676db
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 596161cd2ccf5d4f9a492bbdd23cd8f6f22c5c2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995235"
---
# <a name="handling-encoding-in-a-disassembler-pipeline-component"></a><span data-ttu-id="f5c9f-102">逆アセンブラー パイプライン コンポーネントでのエンコードの処理</span><span class="sxs-lookup"><span data-stu-id="f5c9f-102">Handling Encoding in a Disassembler Pipeline Component</span></span>
<span data-ttu-id="f5c9f-103">カスタム逆アセンブラー コンポーネントが次の形式のいずれかで送信ドキュメントをエンコードすることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f5c9f-103">Ensure that your custom disassembler component encodes outbound documents in one of the following formats:</span></span>  
  
- <span data-ttu-id="f5c9f-104">UTF-8</span><span class="sxs-lookup"><span data-stu-id="f5c9f-104">UTF-8</span></span>  
  
- <span data-ttu-id="f5c9f-105">UTF-16</span><span class="sxs-lookup"><span data-stu-id="f5c9f-105">UTF-16</span></span>  
  
- <span data-ttu-id="f5c9f-106">UTF-32</span><span class="sxs-lookup"><span data-stu-id="f5c9f-106">UTF-32</span></span>  
  
- <span data-ttu-id="f5c9f-107">UTF-16LE</span><span class="sxs-lookup"><span data-stu-id="f5c9f-107">UTF-16LE</span></span>  
  
- <span data-ttu-id="f5c9f-108">UTF-16BE</span><span class="sxs-lookup"><span data-stu-id="f5c9f-108">UTF-16BE</span></span>  
  
  <span data-ttu-id="f5c9f-109">オーケストレーション エンジンでは、他のエンコード形式を使用してドキュメントを処理できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5c9f-109">The orchestration engine may not be able to process documents with other encoding formats.</span></span>  
  
  <span data-ttu-id="f5c9f-110">UTF-32LE と UTF-32BE は .NET Framework ではサポートされていません。これらの形式を使用するには、カスタム エンコード実装を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c9f-110">UTF-32LE and UTF-32BE are not supported by the .NET Framework; to use these formats, you must create a custom encoding implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c9f-111">参照</span><span class="sxs-lookup"><span data-stu-id="f5c9f-111">See Also</span></span>  
 [<span data-ttu-id="f5c9f-112">逆アセンブラー パイプライン コンポーネントの開発</span><span class="sxs-lookup"><span data-stu-id="f5c9f-112">Developing a Disassembling Pipeline Component</span></span>](../core/developing-a-disassembling-pipeline-component.md)